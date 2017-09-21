# gradle에서 테스트를 분리하여 관리/실행하는 방법

> test를 분리해야 하는 이유?  
> unit test, integration test, isolated api test, contract test 등  
> 여러 종류의 테스트를 JUnit 같은 유닛 테스트 코드로 작성하게 된다.  
> 각 테스트를 빌드 파이프라인에서 별도로 실행하는 등 별도의 관리가 필요할 때 테스트를 분리하는 것이 편하다.

## 이름으로 구분
테스트 클래스 IntegrationTest, ServiceTest 등의 규칙을 정하여 이름을 짓고, gradle 설정에서 별도로 수행되도록 한다.

```gradle
test {
    useJUnit {
        exclude '**/*IntegrationTests.class'
    }
}
 
task integrationTest(type: Test) {
    useJUnit {
        include '**/*IntegrationTests.class'
    }
}
```

## JUnit Category
IntegrationTest, UnitTest 같은 marker interface를 만들고 각 테스트가 이들 타입을 갖도록 한다.
@Category(IntegrationTest.class) 같은 형태로 테스트 클래스에 애노테이션을 붙인다.

```gradle
test {
    useJUnit {
        includeCategories 'com.moelholm.UnitTest'
    }
}
 
task integrationTest(type: Test) {
    useJUnit {
        includeCategories 'com.moelholm.IntegrationTest'
    }
}
```

## 스프링의 @IfProfileValue 사용

## 소스 디렉토리로 구분

```gradle
sourceSets {
    integrationTest {
        java {
            compileClasspath += main.output
            compileClasspath += main.compileClasspath
            compileClasspath += test.output
            compileClasspath += test.compileClasspath
            runtimeClasspath += test.runtimeClasspath
        }
    }
}
 
task integrationTest(type: Test) { 
    testClassesDir = sourceSets.integrationTest.output.classesDir
    classpath = sourceSets.integrationTest.runtimeClasspath
}
```

## gradle-testsets-plugin 플러그인 사용
https://github.com/unbroken-dome/gradle-testsets-plugin 플러그인 적용

```gradle
plugins {
    id 'org.unbroken-dome.test-sets' version '1.4.2'
}

apply plugin: 'org.unbroken-dome.test-sets'

testSets {
    integrationTest
}
```


참고:
* https://moelholm.com/2016/10/22/spring-boot-separating-tests/
* https://github.com/unbroken-dome/gradle-testsets-plugin






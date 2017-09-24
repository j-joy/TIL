## gradle-testsets-plugin

https://github.com/unbroken-dome/gradle-testsets-plugin

gradle에서 sourceset을 여러개 두는 것처럼, testset을 추가로 만들어 분류할 수 있도록 해주는 플러그인

## 설정 방법

```gradle
plugins {
    id 'org.unbroken-dome.test-sets' version '1.4.2'
}
```
> plugins 블록은 gradle plugin portal( https://plugins.gradle.org/ )로부터 커뮤니티 플러그인도 쉽게 적용할 수 있게 해준다.

```gradle
apply plugin: 'org.unbroken-dome.test-sets'

testSets { // testset 추가
    integrationTest
}
```

```gradle
dependencies{
...
  integrationTestCompile "com.github.tomakehurst:wiremock:2.8.0"
}
// integrationTest를 추가했다면, testCompile처럼 integrationTestCompile로 dependency를 설정할 수 있다.
```

## tips
test set을 분류만 할 뿐, 'test' sourceset에서 'main' sourceset의 소스코드를 참조할 수 있는 것처럼 'test'의 소스 코드를 참조할 수 없다.  
테스트 목적의 test data builder나, 유틸 클래스 같은 것이 있다면, 새로 추가한 testset에도 클래스를 만들어야 한다.  
~~~이 때, dependencies에 test의 runtimeClasspath을 추가하면 test의 클래스를 참조할 수 있다.~~~ // test의 properties 파일까지 덮어버리므로 주의. 이걸 해결하는 방법을 알기 전까지는 tip은 아닌 걸로..  

```gradle
dependencies{
...
  integrationTestCompile sourceSets.test.runtimeClasspath
}
```


## Spring cloud contract

Consumer-driven contracts testing tool

### Producer 
configuration
```gradle
buildscript {
	dependencies {
		classpath "org.springframework.cloud:spring-cloud-contract-gradle-plugin:1.1.3.RELEASE"
	}
}

apply plugin: 'spring-cloud-contract'
apply plugin: 'maven-publish'
apply plugin: 'groovy'

publishing {
	repositories {
		maven {
			url "http://mynexus@@@:8081/repository/maven-snapshots/"
			credentials{ 
				username "xxx"
				password "xxx"
			}
		}
	}
}

dependencies {
  ...
	testCompile("org.springframework.cloud:spring-cloud-starter-contract-verifier:1.1.3.RELEASE")
}

contracts {
	testMode = 'MockMvc' // generate되는 test형태에 대한 설정 mockMvc가 기본값
	contractsDslDir = project.file("${project.rootDir}/src/contractTest/resources/contracts") //Contract 명세파일 디렉토리 위치 설정
	basePackageForTests = 'jjoy.msatestingsample.coffeedelivery.contract' //자동 생성되는 Test파일 디렉토리 위치 설정
	baseClassForTests = 'jjoy.msatestingsample.coffeedelivery.contract.ContractVerifierBase' //자동 생성되는 Test파일의 부모클래스 설정
}
```
write contract

*  {test folder}/resources/contracts/{class name}/shoud_ooo.groovy
* last package name is class name, each groovy file is method.


```groovy
package contracts.Bread

import org.springframework.cloud.contract.spec.Contract

Contract.make {
    description('''
given
when
 /bread/{breadName} was called
then
 return bread object
''')
    request {
        method 'GET'
        url '/bread/bagel'
    }
    response {
        status 200
        body(
                [
                    name:'bagel'
                ]
        )
        headers {
            contentType(applicationJson())
        }
    }
}
```


Consumer configuration
```gradle
dependencies {
 contractTestCompile ("org.springframework.cloud:spring-cloud-starter-contract-stub-runner:1.1.3.RELEASE"){ exclude group :'org.springframework.integration' }
}
```

# Consumer-driven contracts testing
서비스 간의 API 호출이 약속된 대로 수행되는지 검사하는 테스트.  
Integration 테스트를 통해 API contract를 검사할 수 있지만, 시간이 많이 걸리고 문제를 일찍 찾기 어렵다.  
Contract 테스트는 API 호출에 대한 규약만을 검사하므로 빠르고 가볍게 수행할 수 있다.  
빌드 파이프라인에 활용하면 API 서비스 producer가 API spec을 변경하고 배포하기 전에 consumer들이 변경 전 API spec을 사용하고 있는지 알 수 있다.  

MSA(Micro Service Architecture)의 테스팅 전략에 활용하면 좋은 테스트

관련 글
* https://www.thoughtworks.com/radar/techniques/consumer-driven-contract-testing
* https://martinfowler.com/articles/microservice-testing/#testing-contract-introduction

주요 도구
* Spring Cloud Contract : https://cloud.spring.io/spring-cloud-contract/
* Pact : https://docs.pact.io/  

**non-jvm 언어**  
consumer가 javascript 같은 non-jvm 언어일 경우, 
[stub-runner-boot](https://github.com/spring-cloud-samples/stub-runner-boot)를 사용하여 stub을 다운로드 하고, 실행 되도록 한다.  
stub-runner-boot를 fat jar로 빌드한 다음 아래와 같은 명령으로 실행한다.    

```
java -jar stub-runner-boot --stubrunner.ids="com.example.groupid:artifactid:classifier:version:8090" --stubrunner.repositoryRoot="http://localhost:8081/artifactory/libs-release-local"
```

참고: https://stackoverflow.com/a/43514323

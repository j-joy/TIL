Credentials or tokens should not be hard coded in any code, scripts, build configurations, anything.

To avoid hard coding credential data.
 Use environment variable or runtime parameters.

 ### set environment variable
 add configuration in ~/.profile or ~/.bash_profile
 ```
 export MY_DATA=value
 ```

 use environment variable in node code.
 ```javascript
 const mydata = process.env.MY_DATA;
 ```


AWS access keys best practices
>http://docs.aws.amazon.com/ko_kr/general/latest/gr/aws-access-keys-best-practices.html

1. 계정 액세스 키 제거(또는 생성하지 않음)
1. 장기 액세스 키 대신 임시 보안 자격 증명(IAM 역할) 사용
1. 적절하게 IAM 사용자 액세스 키 관리
  * 액세스 키를 코드에 직접 포함하지 않는다.
    1. The AWS credentials file.  
    1. Environment variables.
  * 애플리케이션마다 서로 다른 액세스 키를 사용한다.
  * 주기적으로 액세스 키를 교체한다.
  * 미사용 액세스 키를 제거한다.
  * 가장 중요한 작업에 대해 멀티 팩터 인증을 구성한다.

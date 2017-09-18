AWS S3를 사용하여 간단하게 private gradle(maven) 레파지토리를 구성할 수 있다.

1. AWS IAM 사용자 생성
2. S3 bucket 생성
3. 생성한 IAM 계정에 새 inline policy를 추가
```javascript
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::repo.teamed.io",
        "arn:aws:s3:::repo.teamed.io/*"
      ]
    }
  ]
}
```
4. S3 bucket을 repository에 추가
```gradle
// build.gradle

repositories {
    maven {
        url "s3://myRepo/myLibraryDir"
        credentials(AwsCredentials) {
            accessKey "someKey"
            secretKey "someSecret"
        }
    }
}
```
5. maven-publish 플러그인을 추가하고, publishing 설정을 추가
```gradle
// build.gradle
apply plugin: 'maven-publish'

publishing {
    repositories {
        maven {
            url "s3://myRepo/myLibraryDir"
            credentials(AwsCredentials) {
                accessKey "someKey"
            	secretKey "someSecret"
            }
        }
    }
}
```

참고: https://vtorosyan.github.io/gradle-s3-private-repo/

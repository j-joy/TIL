### 오픈소스 프로젝트에 기여하는 법

#### 용어 정리
* 메인 저장소(Main repository)   
내가 기여하고자 하는 오픈소스 프로젝트의 메인 저장소. 일반적으로 upstream이라고 부른다.

* 내 저장소(My github repository)  
내가 fork해와서 내 계정에 존재하는 저장소. 일반적으로 origin이라고 부른다.

* 로컬 저장소(Local git repository)  
내 로컬 개발환경의 저장소

#### 오픈소스 기여 단계
1. 기여하고자 하는 오픈소스 프로젝트를 fork한다.
1. 내 저장소의 fork한 프로젝트를 clone한다.
1. 메인 저장소와 동기화(synchronize)하기 위해 upstream remote를 생성한다.  
    git remote add upstream https://github.com/monsterz-lab/jangson-json-matcher
1. 작업 브랜치를 생성한다.
1. 버그 수정이나 기능 추가를 한다.
    1. 코드 스타일을 준수한다.
    1. 유닛 테스트가 존재하면 모두 잘 동작하는지 실행해 본다.
    1. 필요하면 테스트 코드를 추가한다.
    1. 문서를 추가하거나 수정한다.
    1. squash, rebase 등 적절히 commit을 정리한다.
1. 변경된 내용을 commit하고, 내 저장소에 push한다.
1. github의 내 저장소 페이지에서 작업한 브랜치를 선택하고, New pull request 버튼을 누른다.
1. 내용을 잘 작성하고 요청을 보낸다.
1. 메인 저장소 주인이 요청을 수용할 때 까지 기다린다.


참고:
https://gist.github.com/MarcDiethelm/7303312

http://www.popit.kr/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-git-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-pull-request-%EB%B3%B4%EB%82%B4%EA%B8%B0/

https://medium.com/hbsmith/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%9D%BC%EA%B8%B0-git-%EA%B7%B8%EB%A6%AC%EA%B3%A0-%EC%A0%80%EC%9E%A5%EC%86%8C-%EB%8B%A4%EB%A3%A8%EA%B8%B0-9f66c98c1cb5

http://guruble.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%9D%98-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%84%B0%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%90%98%EB%8A%94-%EA%B2%83/

https://git-scm.com/book/ko/v2/GitHub-GitHub-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%97%90-%EA%B8%B0%EC%97%AC%ED%95%98%EA%B8%B0

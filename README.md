# Jenkins

- Jenkins 에 대한 이해와 공부
- link : [Jenkins(wiki)](https://ko.wikipedia.org/wiki/%EC%A0%A0%ED%82%A8%EC%8A%A4)

## 기초지식
- CI(Continuous Integration)
  - 지속적인 통합
  - 업데이트된 소스를 지속해서 통합하는 과정
  - CI vs CD(Continuous Deploy) : 지속 배포

![CI구성](https://user-images.githubusercontent.com/56371387/87215187-d5435500-c36e-11ea-8a28-671ac395e9b4.PNG)

- Jenkins 는 plugin 이 엄청 많다.
  - △SVN △Git △Maven 등...
    1. SVN/Git 에서 소스를 받음
    2. complie 한다 (profile)
    3. war 를 옮긴다.
       - 1. 사람이 하기
       - 2. FTP : 보안문제
       - 3. SFTP : 1), 2) 의 문제를 해결할 수 있음 **(SSH)**
- Jenkins 의 배포시기엔 war에 대한 찌꺼기 데이터들을 다 지우고 하게되는데, 이 때 반드시 다른 관여가 있을수 없도록 **Lock** 을 걸어야 함.

- SNAPSHOT vs Release
  - SNAPSHOT : snapshot 네임으로 설정파일을 만들어두면 무조건 최신 snapshot을 배포함
    - maven update 에 snapshot 관련 설정을 check 해둬야 함
    - version 0.0.0 세자리로 관리함
  
  - release 할 때는 snapshot을 모두 찾아서 버전을 1씩 올린다.

## 참고지식
- 하나의 Was에 여러 Applicaion 구동이 가능하다!
  - context root를 다르게 하면 됨
  - **but, 로그가 섞이게 된다.**

- 배포를 할 때, **class** 파일을 직접 옮기는 행위는 절대 하지말 것!
  - 개발서버와 로컬의 환경이 다르기 때문에 문제가 발생할 수 있음

- built tool 변천사
  - Ant
    - build.xml 사용
    
  - Maven
    - pom.xml(project object model) 사용
    - Maven 의 구조는 **코딩** 하기 좋은 구조이지 **실행** 하기 좋은 구조는 아님!!
    - 코딩 -> 빌드 -> 테스트 -> 조립 -> 배포 (각각이 object)
      - 조립 ≒ 패키징
      - maven 은 패키징으로 **프로젝트 구조** 를 **war** 로 만들어줌
      
- 리눅스/유닉스 vs 윈도우
  - **리눅스/유닉스** 는 디스크의 구분이 없지만, **윈도우** 의 경우 C:, D:, E: 가 나눠져 있다.
  
- JDK vs JRE
  - JDK : Java Development Kit
  
  - JRE : Java Runtime Environment
    - 자바 실행 환경
    - 자바 구동 시 필요한 것
    - Java의 런타임이 필요한 경우 굳이 JDK 까지 보내지 않고 JRE만 담아서 보내는 경우가 많다.

## 로그
- window(PowerShell)


  
  

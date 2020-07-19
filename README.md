# System Under Test

JMeter Dashboard 검토시 사용할 테스트 대상 시스템 코드와 생성 방법에 대한 저장소 입니다.

* jar 파일 생성
    <pre>
    <code>
     . 윈도우에서 실행시 : mvnw clean package
     . Linux(서버)에서 실행시 :  mvnw clean package
       * System-Under-Test 경로에서 실행하면 되고, 파일 권한 'chmod 777 mvnw' 변경해서 실행
    </code>
    </pre>
    
* 실행     
    <pre>
    <code>
    java-jar jroller-sut-0.1.jar
    
    또는
    
    java -jar ./jcontroller-0.0.1-SNAPSHOT.jar

    </code>
    </pre>
    
* 테스트
     <pre>
     <code>
     http://your-domain:8080/greeting
     </code>
     </pre>   
* 참조
    * Building a RESTful Web Service - https://spring.io/guides/gs/rest-service/
    * mvn 설치 방법 - https://www.unixmen.com/install-apache-ant-maven-tomcat-centos-76-5/


<hr/>    

* AWS TIP 
    * ec2 : **프리 티어 사용가능** 표시된 Red Hat 으로 생성
    * 최초 생성 후 기본 id는 ec2-user 로그인 함 
    * root는 **sudo su -** 하여 권한 획득 
    * root에서 **yum install java-11-openjdk-devel** 로 java 설치
    * ec2-user로 sftp 접속히여  jroller-sut-0.1.jar 복사
    * java -jar jroller-sut-0.1.jar 로 시스템 구동 
    * AWS 8080 포트에 대한 인바운드 규칙 생성 
        * console > EC2 > 네트워크 및 보안 > 보안 그룹 > 보안그룹 선택
        * 8080 포트에 대해 열어준다
    * client에서  http://your-ec2-domain:8080/greeting 접속하여 정상 가동 확인
         
        





* CD 예제 설치 및 활용 방법

1. 실행 환경 
예제 실행을 위해서는 JDK 6.0 MySQL 5.1, STS 2.3.2 또는 그 이상의 버전이 필요하다. 모든 예제 프로젝트는 JDK-6u21, MySQL 5.1.40, STS 2.3.2 버전에서 테스트되었다. 버전이나 환경이 다를 경우 일부 테스트가 실패할 수도 있다. 이 때는 테스트를 환경에 맞게 수정해 주거나 환경을 재구성해야 한다.
1.1 JDK 6.0
JDK 6.0 최신버전을 http://java.sun.com/javase/downloads/index.jsp에서 다운로드 받아서 설치한다. 
1.2 MySQL 5.1
MySQL 커뮤니티 버전을 http://www.mysql.com/downloads/mysql/ 에서 다운로드 받아서 설치한다. 설치 옵션은 디폴트로 하되 default character set은 Best Support for Multilingualism(UTF-8)으로 해주는 것이 좋다. 디폴트인 Standard Character Set(Latin1)으로 해도 예제를 실행하는 데는 문제는 없으나 책의 내용을 직접 따라 할 때는 JDBC 드라이버 URL에 ? characterEncoding=UTF-8을 추개해줘야 한다.
1.3 STS 2.3.2
SpringSource Tool Suite(STS)을 http://www.springsource.com/products/springsource-tool-suite-download에서 다운로드 받아서 설치한다. 설치할 때 JDK 6.0의 설치 폴더를 정확히 지정해 줘야 한다. 경우에 따라서 호환되지 않는 JDK버전이라는 메시지가 나오기도 하는데 이는 무시해도 된다.

2. 예제 설치 방법 
예제의 설치를 위해서는 세 가지 작업이 필요하다. 첫째는 예제 프로젝트 파일을 하드디스크로 복사하는 것이고 둘째는 DB 초기화 스크립트를 실행하는 것이다. 마지막으로 STS로 예제 프로젝트를 불러와야 한다.
2.1 예제 복사
예제 프로젝트는 Part1, Part2, springusergroup 세 개의 폴더에 담겨 있다. 각 폴더를 하드디스크의 적당한 위치로 복사한다. 가능하면 영문 이름으로 된 폴더 아래로 복사하는 것이 좋다. 프로젝트 폴더 이름에 한글이 있을 경우 OS에 따라 일부 테스트가 바르게 작동하지 않을 수 있다. 
2.2 MySQL 데이터베이스 초기화
CD의 DB 폴더에 있는 database.sql을 MySQL 커맨드라인 클라이언트나 MySQL 관리 프로그램을 이용해서 실행시킨다. 커맨드라인 클라이언트를 사용하는 경우라면 먼저 database.sql 파일이 있는 폴더로 이동한 뒤에 다음 명령으로 로그인 한다.
mysql ?u root ?p
커맨드라인 모드에서 다음과 같이 database.sql을 실행시킨다.
mysql> source database.sql
2.3 프로젝트 불러오기
먼저 STS를 실행한다. STS 메뉴의 File - Import를 실행시킨다. Import Wizard가 뜨면 General 항목 중에서 Existing Projects into Workspace를 선택한다. 다음 창에서 프로젝트의 루트 디렉토리를 지정해서 프로젝트를 가져올 수 있다. 프로젝트는 한번에 하나 이상을 가져올 수도 있다. 최상위 디렉토리를 선택하면 모든 예제를 한번에 불러올 수도 있다.

3. 실행 방법
Part1과 Part2는 책의 1부와 2부의 예제를 담고 있다. 책의 내용을 참고해서 예제의 코드를 살펴보거나 테스트를 실행할 수 있다.
3.1 springusergroup
Springusergroup은 서버에 배치해서 실행할 수 있는 웹 애플리케이션이다. STS에 내장된 tcServer에 배치해서 실행할 수 있다. Springusergroup 프로젝트를 선택하고 메뉴에서 Run ? Run As ? Run on Server 메뉴를 선택한다. 설치 서버는 SpringSource tc Server 6.0을 선택한다. 서버로 배치가 완료되면 자동으로 STS 내장 브라우저에 첫 화면(로그인 화면)이 뜰 것이다.
만약 Run on Server메뉴 대신 수동으로 서버에 설치했을 경우에는 서버를 직접 실행하고 브라우저에서 http://localhost:8080/springusergroup로 접속하면 된다.

4. Springusergroup 예제 프로젝트
Springusergroup 예제는 2부에서 소개된 스프링의 기술, 특별히 13장의 스프링 @MVC의 활용 예를 보여 주기 위해서 만들어 진 것이다. Springusergroup 예제는 다양한 기술의 활용 방법을 보이기 위해서 만들어 진 것이므로 그대로 실제 프로젝트에 가져다 사용하기에는 적절하지 않다. 책의 내용을 참고해서 코드를 살펴보는 용도로 사용하기를 권장한다. 물론 웹 애플리케이션의 구조는 그대로 가져다 프로젝트 템플릿으로 사용할 수 있다.
springusergroup에는 책에서 설명하지 않은 몇 가지 확장 방법을 보여 준다. 이에 관한 상세한 정보는 저자의 블로그에 있는 책 정보 페이지(http://toby.epril.com/tobyspring3/)를 참고하면 된다.


dependencies {
    compileOnly 'org.projectlombok:lombok'
   	목적 : Getter/Setter 등  Model(DTO, VO, Domain) Object 를 만들때 필요한 메소드, 생성자 등을 직접 코드로 작성하는 수고를 없애주는(반복코드를 어노테이션으로 구현) 라이브러리
  	장점 : 코드 반복 없애줌(불필요하게 비슷한 코드를 반복해서 작성하지 않고 어노테이션으로 해결)
  	단점 : lombok을 사용하여 만들어진 코드를 다른 사람이 컴파일 하기 위해서는 다른 사람들도 모두 lombok을 설치해야 함. (협업을 할때는 lombok을 사용할지 말지 사전에 협의 필요)
    	참조사이트: <https://edoli.tistory.com/99> ,  <https://goddaehee.tistory.com/95> 
    annotationProcessor 'org.projectlombok:lombok'
  	compileOnly 는 <compile시에만빌드하고빌드결과물에는포함하지않음>
   	annotationProcessor 는 <이것을 설정안하면 롬북을 포함해서 프로젝트를 export할 때 롬북에서의 제공되는 에노테이션이 전부 포함되지 않음> 이걸 써줘야 롬복 어노테이션을 롬복 라이브러리에서 정의된 내용으로 보겠다 라는 의미인듯.
	출처: <https://cchoimin.tistory.com/entry/Gradle-annotationProcessor> 

   

    implementation 'org.springframework.boot:spring-boot-starter-actuator'
	스프링 부트 애플리케이션에서 제공하는 여러가지 정보를 모니터링하기 쉽게 해주는 기능
	장점 : 애플리케이션 관리 용이 
	단점 : 외부에 애플리케이션 정보가 노출될 가능성
	출처: https://jeong-pro.tistory.com/160 [기본기를 쌓는 정아마추어 코딩블로그]
		https://supawer0728.github.io/2018/05/12/spring-actuator/


    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
	Jpa를 사용하기 위한 의존성 추가
	JPA를 쓰기 편하게 만들어놓은 모듈
	출처: <https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/> 

    implementation 'org.springframework.boot:spring-boot-starter-data-redis'
	spring에서 redis와 관련한 라이브러리를 추상화시켜서 사용할 수 있게 해준 것
	출처: https://jeong-pro.tistory.com/175 [기본기를 쌓는 정아마추어 코딩블로그]

    implementation 'org.springframework.boot:spring-boot-starter-security'
	Spring security 적용을 위한 의존성 추가
	출처 : https://xmfpes.github.io/spring/spring-security/

    implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
	Thymeleaf 사용을 위한 의존성 추가
	(뷰 템플릿 엔진)
	장점 : 템플릿 코드자체가 그냥 HTML이기 때문에 뷰 파일을 WAS없이도 브라우저에서 직접 띄워볼 수 있다는 점
	단점 : 익숙하지 않다(?)
	출처: <https://blog.outsider.ne.kr/969> 
	
    implementation 'org.springframework.boot:spring-boot-starter-web'
	웹 구축을 위한 스타터, REST 애플리케이션, Tomcat 서버를 내장 서버로 사용
	출처: https://itmore.tistory.com/entry/스프링-부트-입문-이모저모 [IT모아]


    compile 'org.springframework.boot:spring-boot-starter-tomcat'
	스프링 부트에서 Tomcat을 사용하겠다는 의미
	
    // https://mvnrepository.com/artifact/org.hibernate/hibernate-core
    compile group: 'org.hibernate', name: 'hibernate-core', version: '5.4.12.Final'
	하이버네이트 코어 버전 지정
	하이버네이트? -> 
	관계형 데이터베이스(RDBMS)와 객체지향 언어(Java)를 연결해주는 프레임워크
	출처: <https://hun-a.github.io/2017/11/17/hibernate_setting/> 
	[JPA는 기술 명세, 하이버네이트는 JPA의 구현체]
	출처: <https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/> 
	
	
    // https://mvnrepository.com/artifact/com.vladmihalcea/hibernate-types-52
    compile group: 'com.vladmihalcea', name: 'hibernate-types-52', version: '2.9.3'
	하이버네이트 타입을 이용하게 해주는 의존성 추가
	자바 - SQL간 연결을 시켜주는 하이버네이트 타입이 별도로 존재하여 이를 사용하기 위함인듯.
	(type-safe)
	출처: <https://lng1982.tistory.com/285> 
	출처 : https://kwonnam.pe.kr/wiki/java/hibernate/types
	

    compile 'com.querydsl:querydsl-jpa'
	QueryDSL -> 쿼리를 자바 코드로 생성하게 해준다.
	장점 : 컴파일 시점에 쿼리 오류 등을 알 수 있다.
		 코드로 작성하기 때문에 조건문, 동적쿼리 등 작성이 용이하다.
	단점 : 복잡한 통계 쿼리의 경우…? (대부분은 다 가능하다고 한다.)
	출처: <https://ict-nroo.tistory.com/117> 
	
	
    compile 'com.querydsl:querydsl-apt'
	쿼리 타입(Q)를 생성할 때 사용하는 라이브러리
	출처: <https://joont92.github.io/jpa/QueryDSL/> 
	//todo : 내용추가 + 이해 필요
	
	
    compileClasspath 'gradle.plugin.com.ewerk.gradle.plugins:querydsl-plugin:1.0.10'
	querydsl 플러그인(추가기능?) 의존성 등록
	출처: <https://jojoldu.tistory.com/372> 
	
	
    // https://mvnrepository.com/artifact/org.modelmapper.extensions/modelmapper-spring
    compile group: 'org.modelmapper.extensions', name: 'modelmapper-spring', version: '2.3.6'
    // https://mvnrepository.com/artifact/joda-time/joda-time
    compile group: 'joda-time', name: 'joda-time', version: '2.10.5'
    // https://mvnrepository.com/artifact/org.thymeleaf/thymeleaf
    compile group: 'org.thymeleaf', name: 'thymeleaf', version: '3.0.11.RELEASE'
    // https://mvnrepository.com/artifact/org.thymeleaf/thymeleaf-spring5
    compile group: 'org.thymeleaf', name: 'thymeleaf-spring5', version: '3.0.11.RELEASE'
    // https://mvnrepository.com/artifact/org.thymeleaf.extras/thymeleaf-extras-springsecurity4
    compile group: 'org.thymeleaf.extras', name: 'thymeleaf-extras-springsecurity4', version: '3.0.4.RELEASE'
    // https://mvnrepository.com/artifact/nz.net.ultraq.thymeleaf/thymeleaf-layout-dialect
    compile group: 'nz.net.ultraq.thymeleaf', name: 'thymeleaf-layout-dialect', version: '2.4.1'
    implementation 'org.flywaydb:flyway-core'
    developmentOnly 'org.springframework.boot:spring-boot-devtools'
    // https://mvnrepository.com/artifact/com.fasterxml.jackson.datatype/jackson-datatype-joda
    compile group: 'com.fasterxml.jackson.datatype', name: 'jackson-datatype-joda', version: '2.10.2'
    // https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
    compile group: 'com.squareup.okhttp3', name: 'okhttp', version: '4.4.0'

    compile 'mysql:mysql-connector-java'
    runtime 'org.mariadb.jdbc:mariadb-java-client:2.3.0'

//    ######################################################################################
    testImplementation('org.springframework.boot:spring-boot-starter-test') {
        exclude group: 'org.junit.vintage', module: 'junit-vintage-engine'
    }
    testImplementation 'org.springframework.restdocs:spring-restdocs-mockmvc'
    testImplementation 'org.springframework.security:spring-security-test'
    testAnnotationProcessor 'org.projectlombok:lombok'
    testCompileOnly 'org.projectlombok:lombok'
    //     https://mvnrepository.com/artifact/org.hamcrest/hamcrest
    testCompile group: 'org.hamcrest', name: 'hamcrest', version: '2.2'
	JUnit에 사용되는 Matcher 라이브러리 - 
	필터나 검색등을 위해 값을 비교할 때 좀 더 편리하게 사용하도록 도와주는 라이브러리
	출처: <http://blog.naver.com/PostView.nhn?blogId=simpolor&logNo=221289242597&parentCategoryNo=&categoryNo=166&viewDate=&isShowPopularPosts=false&from=postView> 
}

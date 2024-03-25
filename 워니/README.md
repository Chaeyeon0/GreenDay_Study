### **1. 스프링**

- 자바 개발 편하게 해주는 프레임워크
-configuration해주는 class들이 많다

### **2. 스프링부트**

- 스프링으로 처리해야 하는 설정들을 간편하게 해주는 프레임워크 편하게 사용 가능
- 가져다 쓰는데 큰 의미가 있음 -> 커스텀마이징할수록 스프링부트의 장점을 희미하게 함

### **JDBC**

- 서버랑 데이터베이스 연결해주는 API

### **4. 애플리케이션을 만드는 이유**

- 애플리케이션(Application) - 사용자가 특정 작업을 수행할 수 있도록 도와주는 소프트웨어 프로그램이에요. 예를 들어, 문서를 작성하거나 편집할 수 있는 '워드 프로세서', 인터넷을 탐색할 수 있는 '웹 브라우저', 메시지를 주고받을 수 있는 '메신저 앱' 등이 애플리케이션의 예
- 데이터를 받고 DB에서 가공을 하고 나서 반환해줌(여기서 DB는 애플리케이션이 필요로 하는 데이터를 저장하고 반환해주고 찾아줌)

> [!Note]
> 애플리케이션 구조의 큰 틀

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/51fa8787-1b9f-4318-a21d-c71be7bee983/7104c048-b59d-44cc-99f5-f508430315ee/Untitled.png)

→ 데이터가 input, 그러니까 회원가입을 하면 App은 회원가입이라는 프로세싱을 마치게 되고, 개인정보가 DB에 들어감. output에서는 마무리하게 됨.

### **5. `input`을 받음**

- 보통 `controller`라고 함

### **6. MVC 패턴**

- 디자인 패턴으로, **Model(데이터베이스), View(화면단), Controller(input을 받는 위치)의 줄임말**로 어플리케이션을 구성할 때 그 구성요소를 세가지의 역할로 구분
- 비즈니스 로직(데이터를 받아서 프로세싱하고 리턴값으로 돌려주는 output의 관계)를 분리하여 서로 영향없이 쉽게 고칠 수 있는 설계가 가능

> 💡**7컨트롤러**
> 
- 모델과 뷰 사이에 브릿지 역할을 수행 → ex) 뷰에서 회원가입을 하면 컨트롤러에서 값을 받아서 모델쪽으로 생성을 해줌
- 사용자의 요청은 모두 컨트롤러를 통해서 진행되어야 함

> **모델**
> 
- 데이터를 처리하는 영역
- 데이터베이스와의 연동을 위한 것 - 엔티티 쪽을 생각하면 됨.
- ex) 검색을 위한 키워드가 넘어오면 데이터베이스에서 관련된 상품의 데이터를 받아 뷰에 전달

> **뷰**
> 
- 데이터를 보여주는 화면 자체의 영역을 뜻함
- 뷰에서는 별도의 데이터를 보관하지 않음
- 예) 검색 결과를 보여주기 위해 모델에서 결과 상품 리스트 데이터를 받음

*레이어드 아키텍처 - 기본 베이스이다.*

→ 일반적인 구조: 컨트롤러에서 요청이 들어오면 service로 전달하고, 레포지토리로 전송해서 데이터베이스와 연결하는 구조

### 7. Rest API

> 컨트롤러로 요청을 받을 때 통신하는 것 → 프론트엔드와의 통신에서 중요한 역할을 함
> 
- API(Application Programming Interface) 의 줄임말
- API: 응용 프로그램에서 사용할 수 있도록 다른 응용 프로그램을 제어할 수 있게 만든 인터페이스
- API 사용하면 내부 구현 로직을 알지 못해도 정의되어있는 기능을 쉽게 사용할 수 있음

<aside>
💡 여기서 인터페이스란?

</aside>

→ 어떤 장치간 정보를 교환하기 위한 수단이나 방법을 의미함, 대표적인 인터페이스는 마우스/키보드/터치패드 등

- Rest: 자원의 이름으로 구분하여 해당 자원의 상태를 교환하는 것을 의미
- Rest API: 웹 기반의 API 중 하나

       → 서버와 클라이언트의 통신 방식 중 하나임 (웹 서비스에 특화됨)

- HTTP URL을 통해 자원을 명시하고 HTTP Method를 통해 자원을 교환함
- REST API는 상태를 유지하지 않는(stateless) 특성을 가짐
- HTTP Method : Create, Read, Update, Delete

> Rest API와 API의 차이점
> 

API는 로컬 또는 웹 기반일 수 있으며, 다양한 프로토콜과 기술을 사용할 수 있음. REST API는 HTTP 프로토콜을 기반으로 하며, 웹 상에서 자원의 상태를 주고받는데 사용됨. REST API는 특정 규칙(예: 상태를 유지하지 않음, 표준 HTTP 메소드 사용)을 따르는 반면, 일반 API는 이러한 제한이 없을 수 있습니다.

### 8. 아파치 톰캣 웹서버 WAS의 차이

- 아파치 - 가장 널리 사용되는 웹서버 소프트웨어 중 하나이고, 클라이언트로부터 HTTP 요청을 받아서 정적인 콘텐츠 제공
- 톰캣 - 웹 어플리케이션 서버의 일종이고, 동적 컨텐츠 제공하는 자바 웹 애플리케이션에 주로 사용됨
- 웹서버 - 정적인 콘텐츠에서 주로 사용되는 서버, 아파치가 대표적인 예
- WAS - 동적 컨텐츠 제공하기 위해 사용되는 서버, 톰캣이 대표적인 예
- JDK - 자바 프로그램을 개발할 때 꼭 필요한 프로그래밍 도구 → 자바 프로그램을 컴파일하고 실행할 수 있는 컴파일러(javac), 자바 가상 머신(JVM), 그리고 다양한 라이브러리와 도구들이 포함되어 있음
- eclipse - 자바 개발을 위해 널리 사용되는 개발 환경(보다 쉽고 효율적으로 만들어주는 통합 개발 환경) → Eclipse와 같은 IDE는 코드 작성, 디버깅, 빌드 자동화, 버전 관리 등의 기능을 제공하여 개발 과정을 더욱 편리하게 만들어 주지만, 기본적으로 자바 프로그램을 개발하고 실행하기 위해 꼭 필요한 것은 아닙니다.

### 9. 회원가입 부분

- 레포지토리 부분

---

   Member

     l

     l

   controller            -               repository   -       service

     l                                      l                    l

MemberController.java                     entity          Memberservice

                                            l

                                         User.java

---

<aside>
>💡`User`가 들어가게 레포지토리 이름을 구성하면 User가 애초에 예약어여서 오류가 생김

</aside>

- `@GetMapping` - 자원을 가져오는 역할
- `@PostMapping` - 넣어주는 역할

→ `/join` : 회원가입을 통해 회원들의 정보를 서버에게 전달

- repository/ `@Entity` - 어떤 값들을 받을 것인가, 회원 가입을 통해서 어떤 값들을 저장할 것인가

→ 역할 - 테이블 설계를 함

```java
@Entity
@NoArgsConstructor // 생성자
@AllArgsConstructor( access = AccessLevel.PRIVATE)
@Builder
@Getter // 생성자
public class Member{
// 여기 안에 들어가는 변수들을 기준으로 데이터 칼럼을 구성해준다.
	@Id  // 엔티티 만들면 필요하게 되는 부분
	@GeneratedValue( strategy = GenerationType.IDENTITY) // 자동으로 auto_increme - 자동으로 데이터가 들어올 때마다 체계적으로 짜준다.
  private Long index; // @Id 부분
  
  private String id;
  
  private String name;
  
  private String phonenumber;
}
```

<aside>
>💡 `private` 으로 하는 이유 : 접근하지 못하게 하기 위한 하나의 보안 차원의 설계 방법

</aside>

→ 확인하는 방법 : H2 콘솔을 이용해서 `select * from mamber;` 를 쓰면 됨

- JPA
    - 자바의 ORM기술을 쉽게 구현하도록 도와주는 API
    - 자바에서 객체를 데이터베이스에 저장하고 관리하기 위한 인터페이스와 기능을 제공하는 API
    - SQL Mapper는 ‘**개발자가 작성한 SQL 실행 결과를 객체에 매핑**’시켜주는 프레임워크이며, ORM은 객체와 DB의 데이터를 ‘**자동으로 매핑**’시켜주는 프레임워크 → **SQL Mapper 기술을 제공하는 것이 ‘MyBatis’이며, ORM 기술을 제공하는 것이 ‘JPA(Java Persistence [Api](https://www.elancer.co.kr/blog/view?seq=199))’**
![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/51fa8787-1b9f-4318-a21d-c71be7bee983/06fb937e-69ba-4c5a-9900-f79f02fae4eb/Untitled.png)
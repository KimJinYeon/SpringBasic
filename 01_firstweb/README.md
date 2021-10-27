# Servlet을 이용해서 간단한 페이지 만들기

### Servlet이란?

    자바 웹 어플리케이션의 구성요소 중 동적인 처리를 하는 프로그램의 역할.
    정적인 페이지는 JSP로 구성한다고 한다.

### Servlet 3.0 이상 spec과 미만 spec의 차이점

    Servlet 3.0 미만에서는 web.xml을 이용한다.
    Servlet 30. 이상에서는 annotation을 이용한다.

### doGet 메소드를 이용해서 간단한 페이지 만들기

    response와 request를 이용해서 웹 페이지에 콘텐츠를 출력할 수 있다.
    HttpServletRequest와 HttpServletResponse 클래스에서 관련 메소드를 제공한다.

### Servlet의 lifecycle 이해하기

    메모리에 호출하는 Servlet이 있는지 확인한다.
    없으면 생성하고 init 메소드를 실행한다.
    service 메소드를 실행한다.
    WAS가 종료되거나 웹 어플리케이션이 수정되었을 경우 destroy 메소드가 실행된다.
    service 메소드는 템플릿 메소드 디자인 패턴으로 만들어져있다.

### doGet()과 doPost()로 정보를 넘겨받는 페이지 만들기

    한글을 제대로 인코딩하지 못하는 문제가 발생했다.
    해결방법: 사용자로부터 정보를 받을 때, 사용자에게 다시 정보를 출력할 때 모두 encoding이 UTF-8이라고 명시한다.
    1. doGet()의 <form> 태그에 accept-charset='UTF-8' 추가
    2. doPost()에 request.setCharacterEncoding("UTF-8"); 추가
    3. response.setContentType("text/html;charset=UTF-8"); 추가
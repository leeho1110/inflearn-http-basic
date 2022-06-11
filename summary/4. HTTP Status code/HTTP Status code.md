# HTTP Status code

- 2XX
    - 200 OK: 요청 성공
    - 201 Created: 요청 성공하여 새로운 리소스가 생성됨
    - 202 Accepted: 요청이 접수되었으나 처리가 아직 완료되지 않음
    - 204 No Content : 요청은 성공적으로 수행했지만, 응답 페이로드 본문에 보낼 데이터가 없음
- 3XX
    - 301 Moved Permanently: 리다이렉트 시 요청 메서드가 GET으로 변하며, 본문이 제거될 수 있음
    - 302 Found: 내용은 위와 동일
    - 307 Temporary Redirect: 리다이렉트 시 요청 메서드와 본문을 유지하며 이를 변경해서는 안된다.
    
    > ***PRG Pattern (POST, Redirect, GET)***
    > 
    
    POST를 통해 주문을 진행한다고 해보자. 새로고침을 입력한다면 주문할 때 입력던 URI를 다시 요청하기 때문에 중복 주문이 발생할 수 있다. 
    
    따라서 우리는 이를 해결하기 위해 PRG 패턴을 사용한다. 주문(POST) 후에는 주문 결과 화면을 GET 메서드로 요청할 수 있도록 리다이렉트 응답을 전송한다. 이렇게 처리하게 되면 새로고침을 해도 GET 요청으로 받아온 주문 결과화면만 노출되고 POST 요청 URI는 중복되지 않는다.
    
- 4XX (Client Error)
    - 400 Bad Request: 클라이언트가 잘못된 요청을 해서 서버가 요청을 처리할 수 없음
    - 401 Unauthorized: 인증되지 않음, WWW-Authenticate 헤더와 인증 방법을 설명
        - 인증(Authentication) : 본인 확인(로그인)
        - 인가(Authorization): 권한 부여 (Admin 권한같은 특정 리소스에 접근할 수 있는 권한)
    - 403 Forbidden : 인증 자격 증명은 있지만 접근 권한이 불충분한 경우
    - 404 Not Found: 요청 리소스가 서버에 없음
- 5XX (Server Error)
    - 500 Internal Server Error: 서버 문제로 오류가 발생한 경우
    - 503 Service Unavailable: 서비의 일시적인 과부하 또는 예정된 작업으로 요청을 처리할 수 없음
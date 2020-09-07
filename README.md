

blog.hkwon.me/ab-apache-http-server-benchmarking-tool/

    ubuntu : sudo apt-get install apache2-utils

    주요 옵션
    -n 성능 검사를 위해 보내는 요청 수
    -c 동시 접속수 (client)
    -C Cookie 헤더
    -H 요청에 헤더 추가
    -i GET 대신 HEAD 요청
    -k KeepAlive
    -p POST

    사용법 예시
    $ ab -n 100 -c 10 http://192.168.0.108:9001/token
    
    - 10명이 10번 요청

    $ sudo apt-get install -y gnuplot
    
    $ ab -n 100 -c 10 -g result.plot http://192.168.0.108:9001/token
    
    $ cat  result.plot
    
    starttime : request가 시작된 시간
    seconds : starttime을 unix timestamp로 표현
    ctime : connection 시간으로 request를 write하기 위해 서버와 socket을 여는 시간
    dtime : processing 시간 -> 결과를 반환받기 위해 wait하는 시간 + 서버 작업 시간 + 결과 반환 시간.
    dtime = ttime – ctime
    ttime : request가 전체 수행된 시간(ttime = ctime + dtime)
    wait : request를 보내고나서 response를 받기 전까지 서버사이드에서 처리되는 시간
    network 시간 = dtime – wait
    
    starttime	seconds	ctime	dtime	ttime	wait
    Mon Sep 07 17:08:49 2020	1599466129	133	505	638	361
    Mon Sep 07 17:08:50 2020	1599466130	199	949	1148	949
    Mon Sep 07 17:08:50 2020	1599466130	199	950	1149	950
    
    # 터미널 사이즈 조정(이미지 사이즈)
    set terminal png size 1024,768

    # 가로, 세로 비율
    set size 1,0.5

    # 결과 파일 설정
    set output "result.png"

    # 범례/key 위치
    set key left top

    # y축 grid line
    set grid y

    # Label the x-axis
    set xlabel 'requests'

    # Label the y-axis
    set ylabel "response time (ms)"

    # Tell gnuplot to use tabs as the delimiter instead of spaces (default)
    set datafile separator '\t'

    # Plot the data
    plot "result.plot" every ::2 using 5 title 'response time' with lines
    exit
    
    $ gnuplot script.plot
    
    request별 response time을 그래프로 확인해 볼 수 있는데, 다음과 같이 호출한 시간 별로 scatter chart처럼 그래프를 그려볼 수도 있다.
    
    # 터미널 사이즈 조정(이미지 사이즈)
    set terminal png size 1024,768

    # 결과 파일 설정
    set output "result.png"

    # 범례/key 위치
    set key left top

    # y축 grid line
    set grid y

    # x축 데이터 지정
    set xdata time

    # input time format
    set timefmt "%s"

    # x축 time format 시:분:초
    set format x "%H:%M:%S"

    # Label the x-axis
    set xlabel 'H:M:S'

    # Label the y-axis
    set ylabel "response time (ms)"

    # 구분자로 탭을 사용
    set datafile separator '\t'

    # Plot the data
    plot "result.plot" every ::2 using 2:5 title 'response time' with points

    exit




JWT (Json Web Token)

https://www.pingidentity.com/developer/en/resources/jwt-and-jose.html

    Claim	Description
    iss  Issuer of the JWT; 토큰 발급자
    sub  Subject that the JWT is representing ; 토큰의 대상
    aud  Audience for the JWT ; 토큰 수신자
    exp  Time the JWT is set to expire ; 토큰의 만료 시간
    nbf  Time the JWT is valid from (not-before) ; 토큰의 not-before 타임, 언제 토큰이 유효해지기 시작하는지를 
    iat  Timestamp when the JWT was issued (issued-at) ; 토큰이 발급된 시간
    jti  Unique identifier for the JWT (JWT ID) ; 토큰 식별자, 토큰 발급자가 생성한 토큰의 고유한 식별자 값
    
    ex) 
    
    {
        "iss":"https:\/\/localhost:9031",
        "sub":"joe",
        "aud":"im_oic_client",        
        "exp":1394061153,
        "iat":1394060853,        
        "jti":"uf90SK4wscFhctUT6Dtvb2",
        "nonce":"e957ffba-9a78-4ea9-8eca-ae8c4ef9c856",
        "at_hash":"wfgvmE9VxjAudsl9lc6TqA"
    }
    
라즈베리파이 모델 버전 확인 방법

    $ cat /proc/cpuinfo
    processor       : 0
    model name      : ARMv6-compatible processor rev 7 (v6l)
    BogoMIPS        : 2.00
    Features        : half thumb fastmult vfp edsp java tls
    CPU implementer : 0x41
    CPU architecture: 7
    CPU variant     : 0x0
    CPU part        : 0xb76
    CPU revision    : 7

    Hardware        : BCM2708
    Revision        : 000d
    Serial          : xxxxxxxxxxxxxxxx

    evision 별 Raspberry Pi 모델

    0002 오리지널 Model B. 메모리 256MB
    0003 오리지널 Model B with no polyfuses. 메모리 256MB
    0004 Model B. 메모리 256MB
    0005 Model B. 메모리 256MB
    0006 Model B. 메모리 256MB
    0007 Model A. 메모리 256MB
    0008 Model A. 메모리 256MB
    0009 Model A. 메모리 256MB
    000d Rev2 Model B. 메모리 512MB
    000e Rev2 Model B. 메모리 512MB
    000f Rev2 Model B. 메모리 512MB
    a21041 Raspberry Pi 2 Model B. 메모리 1GB


http://raspberryalphaomega.org.uk/2013/02/06/automatic-raspberry-pi-board-revision-detection-model-a-b1-and-b2/










oauthlib
https://oauthlib.readthedocs.io/en/latest/faq.html

requests-oauthlib
https://requests-oauthlib.readthedocs.io/en/latest/oauth2_workflow.html#introduction

# paper
paper

    sudo apt update
    python -m venv paper
    cd paper
    source bin/activate
    cd ..

1 install for oauthlib

    apt-get install python3-oauthlib
    pip install pyjwt cryptography

2 install for client

    pip install requests-oauthlib
  
  https://oauthlib.readthedocs.io/en/latest/oauth2/clients/client.html
  
3 Provider

 https://oauthlib.readthedocs.io/en/latest/oauth2/server.html
 
 Django django-oauth-toolkit
 
 
--------------------------------------------------------------------------

      OAuth 플로 인가 그랜트 영역
      1. 인가 그랜트 타입
      서로 다른 구성요소들 간의 정보를 별도로 유지한다.

      2. 클라이언트 자격 증명
      명시적인 리소스 소유자가 없거나 리소스 소유자와 클라이언트 소프트웨어를 구별하기 힘들 때 사용

      3. 리소스 소유자 자격 증명
      사용자 이름과 비밀번호를 가진 클라이언트가 액세스 토큰과 교환 할 수 있는 방식

      4. 에설션 그랜드 
      확장된 그랜트 타입
      졸업장이나 자격증과 같은 일종의 인증된 문서, 
      SAML(Security Assertion Markup Language)과 JWT(Json Web Token) 사용



      1 OAuth2.0이 무엇인가?
      2 OAUth 기본
        - 엑세스 토큰
        - 범위
        - 리프레시 토큰
        - 인가 그랜트
      << 구현 >>
      3 OAuth Client: Access Token은 램덤 값으로 제공
      4 OAuth Resource: Access Token은 램덤 값으로 제공
      5 OAuth Server: Access Token은 램덤 값으로 제공
      6 그랜트 타입 종류와 특징
        - 암시적 그랜트 타입
        - 클라이언트 자격 증명
        - 리소스 소유자 자격 증명
        - 어설션 그랜트
      << 취약점 >>
      7 클라이언트 보안 취약점
      8 리소스 보안 취약점
      9 인가 서버 보안 취약점
      10 토큰 보안 취약점
      << OAuth 토큰>>
      11 토큰이란
         - JWT 구조
         - JOSE (JSON Object Signing and Encryption, 서명: JSON Signatures, 암호: JSON Web Encryption)
           * HMAC 시그니처 대칭 서명과 검증
           * RSA 시그니처 비대칭 서명과 검증
           * JSON Web Keys, JWK
         - 인트로스팩션
         - 토큰 폐기
      12 클라이언트 동적 등록
      13 사용자 인증
         - OpenID
      14 프로토콜과 프로파일
        - UMA 프로토콜 동작 방식
        - HEART
        - iGOV
      15 PoP 토큰
  
    
 

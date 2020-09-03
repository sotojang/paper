
JWT (Json Web Token)

https://www.pingidentity.com/developer/en/resources/jwt-and-jose.html

    Claim	Description
    iss  Issuer of the JWT; 토큰 발급자
    sub  Subject that the JWT is representing ; 토큰의 대상
    aud  Audience for the JWT ; 토큰 수신자
    exp  Time the JWT is set to expire ; 토큰의 만료 시간
    nbf  Time the JWT is valid from (not-before) ; 토큰의 not-before 타임, 언제 토큰이 유효해지기 시작하는지를 
    iat  Timestamp when the JWT was issued (issued-at) ; 코큰이 발급된 시간
    jti  Unique identifier for the JWT (JWT ID) ; 토큰 식별자, 토큰 발급자가 생성한 코큰의 고유한 
    
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
  졸업장이나 자격증과 같은 일종의 인증된 문서, SAML(Security Assertion Markup Language)과 JWT(Json Web Token) 사용
  
  
  
  
  
  




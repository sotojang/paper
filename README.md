
JWT (Json Web Token)

https://www.pingidentity.com/developer/en/resources/jwt-and-jose.html

    Claim	Description
    iss	    Issuer of the JWT
    sub	    Subject that the JWT is representing
    aud	    Audience for the JWT
    exp	    Time the JWT is set to expire
    nbf	    Time the JWT is valid from (not-before)
    iat	    Timestamp when the JWT was issued (issued-at)
    jti	    Unique identifier for the JWT (JWT ID)
    
    ex) 
    
    {
        "sub":"joe",
        "aud":"im_oic_client",
        "jti":"uf90SK4wscFhctUT6Dtvb2",
        "iss":"https:\/\/localhost:9031",
        "iat":1394060853,
        "exp":1394061153,
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
 
 
  
  

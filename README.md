# freenom-SSL-guide
# SSL 인증 가이드
===
 Installation environment
---
 PC : MacOS <br>
 
## Index
1. Overview
 
## Overview
http://www.freenom.com/en/index.html?lang=en

에서 로그인 후 도메인 주소 받기 ( 필요한 OS : Linix , MacOS )

https://certbot.eff.org 

접속 후 software , system 고르기 ( 도메인 할당 받을때 적은 IP PC)

```
Ex) None, Ubunto
Install
On Ubuntu systems, the Certbot team maintains a PPA. Once you add it to your list of repositories all you'll need to do is apt-get the following packages.

$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install certbot 
```

install 과정 실행을 한다.

설치가 완료되면 다음 명령어를 실행한다.


```
$ sudo certbot certonly --standalone -d example.com -d www.example.com
```

명령어 실행 후 성공했을 때 다음과 같이 출력된다.

```
Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/example.com/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/example.com/privkey.pem
   Your cert will expire on 2017-12-15. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot
   again. To non-interactively renew *all* of your certificates, run
   "certbot renew"
```

성공했다면 /etc/letsencrypt/archive 폴더에 해당 주소를 가진 폴더가 생성됨.

그안에 4개의 파일이 들어있다.

```
cert1.pem  chain1.pem  fullchain1.pem  privkey1.pem
```

4개의 파일이 생성된 뒤에 freenom 사이트에 my domain에 가서 설정을 들어간다.

설정에서 내가 사용하고자 하는 IP로 바꿈 ( Node 서버가 돌아가는 PC IP )

그 인증서를 사용해서 node 서버를 구현한다.




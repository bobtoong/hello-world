AWS EC2 생성(free tier, WORDPRESS 사용)
freenom.com에서 Domain 생성 -> bobtoong.ga
AWS에 elastic ip 생성
ROUTE 53 에 hosted zone 생성하고, 3번의 elastic ip 연결
 이때 NS record에 만들어진 name server를 freenom.com의 domain 관리 -> nameserver에 추가
 그러면 bobtoong.ga로 AWS EC2로 만들어 놓은 Cloud server에 접속 가능
 
 
 http://sblog.netraweb.com/setup-external-domain-aws/
 
Putty를 이용한 console 연결
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html


AWS에 웹서버 설치
https://blog.lael.be/post/6586


Timezone 변경

[ec2-user@ip-172-31-7-180 ~]$ date
Fri Aug  8 06:41:49 UTC 2014 

[ec2-user@ip-172-31-7-180 ~]$ sudo date
Fri Aug  8 06:42:01 UTC 2014 

[ec2-user@ip-172-31-7-180 ~]$ sudo cat /etc/localtime
TZif2UTCTZif2UTC
UTC0 

[ec2-user@ip-172-31-7-180 ~]$ sudo rm /etc/localtime 

[ec2-user@ip-172-31-7-180 ~]$ sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime 

[ec2-user@ip-172-31-7-180 ~]$ date
Fri Aug  8 15:48:27 KST 2014 

[ec2-user@ip-172-31-7-180 ~]$ sudo date
Fri Aug  8 15:48:40 KST 2014

root password 설정
$ sudo su
# passwd root 	// 생성
# passwd –d root  // 삭제

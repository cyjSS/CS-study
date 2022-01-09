IP 주소
=======

IP Address
-----------
* 네트워크 통신에 있어 각각의 통신기기에 할당된 식별번호
* 통신기기마다 고유하게 할당되는 것X 통신사에 일정 금액을 지불하고 받아오는 것
  
IP 구조
---------
   ![image](https://user-images.githubusercontent.com/92037407/140609394-11f7881e-887e-4a79-b996-f60ca1cd2faf.png)   
+ 32bit(4byte) 길이로 구성된 논리적인 주소체계
+ 십진수 표기법 ex) 172.168.10.1 => 이러한 표기법을 dot-decimal notice 또는 dotted-quad sequence라고 부른다.
+ .(dot)으로 구분된 Octet(8bit/1byte) 4개가 조합
+ 각 옥텟별로 0~255까지의 범위
+ 전체 IP의 수는 약 43억개 정도로 한정

IP 주소의 Network ID와 Host ID
-------------------------------
하나의 IP 주소 = Network ID와 Host IP가 존재
* Network ID: 인터넷 상에서 모든 Host들을 전부 관리하기 힘들기에 한 Network의 범위를 지정해 관리하기 쉽게 만들어 낸 것
* Host ID: 호스트들을 개별적으로 관리하기 위해 사용하게 된 것
  
IP Class 개념
-------------
IP Class의 경우 A,B,C,D,E Class로 나누어 Network ID와 Host ID를 구분   
* ![image](https://user-images.githubusercontent.com/92037407/140610112-68dba3d5-a21c-4c2f-aded-4514a026ac22.png)

* A Class
  * 처음 8bit가 Network ID이며, 나머지 24bit가 Host ID
  * 비트가 0으로 시작하기에 네트워크 할당은 0~127
  * 즉 128곳에 네트워크 할당, 최대 호스트 수는 16777214개(256 *256 *256-2)
  * 대규모 네트워크 환경용
* B Class
  * 처음 16bit가 Network ID이며, 나머지 16bit가 Host ID 
  * 비트가 10으로 시작하기에 네트워크 할당은 16384곳 가능(64 *256)
  * 최대 호스트 수는 65534개(256 *256-2)
  * 중규모 네트워크 환경용
* C Class
  * 처음 24bit가 Network ID이며, 나머지 8bit가 Host ID
  * 비트가 110으로 시작하기에 네트워크 할당은 2097152곳 가능(32 *256 *256)
  * 최대 호스트 수는 254개(256-2)
  * 소규모 네트워크 환경용
* D Class
  * Multicast(멀티캐스트) => 실제 사용되는 경우 거의 X
* E Class
  * 연구/개발용 IP주소 혹은 미래에 사용하기 위해 남겨둔 것 => 실제 사용되는 경우 거의 X

  ![image](https://user-images.githubusercontent.com/92037407/140610127-f035b9ce-0d89-4205-8863-9033c1684284.png)   
  
  IPv4와 IPv6
  -----------
  * 기하급수적으로 늘어나는 사용자 수요 => IPv4 부족
  * 128bit를 16bit씩 8부분으로 나누어 각 부분을 콜론(:)으로 구분하여 표현, 각 구분은 16진수로 표현
  * 예) 2001:230:abcc:ffff:0000:0000:ffff:1111
  * 실시간 서비스를 더욱 쉽게 제공, 인증, 데이터 무결성, 데이터 기밀성을 지원하도록 보안기능을 강화한 것
  * A,B,C,D와 같은 클래스별 할당방식을 사용하지 않아 주소의 낭비 요인이 사라지고 더욱 간단하게 주소를 자동 설정 가능

  ![image](https://user-images.githubusercontent.com/92037407/140610873-3a3a1a54-2dbc-4332-b532-7c264e9765ce.png)   
  ## IPv4에서 IPv6로 변환
  * 이중 스택: 모든 인터넷이 IPv6를 사용하기 전까지 시스템은 IPv4와 IPv6를 동시에 지원
  * 터널링(tunneling) 
    * IPv6를 사용하는 두 호스트가 통신을 할 때 패킷이 IPv4를 사용하는 지역을 지나는 경우에 사용 가능한 방법
    * IPv4 지역에 들어서면 IPv6 패킷은 IPv4 패킷으로 캡슐화하고 이 지역을 벗어날 때 역캡슐화
    * ![image](https://user-images.githubusercontent.com/92037407/140953492-a8022dd9-bda2-4434-bdb8-7ce66c3bbb10.png)

  * 헤더 변환(header translation)
    * IPv4 주소를 IPv6 주소로 변환 또는 그 반대로 변환하여 통신
    * ![image](https://user-images.githubusercontent.com/92037407/140953437-7befa5de-db68-4c4f-aced-2840ea29f1ab.png)
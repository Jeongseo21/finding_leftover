# finding_leftover
>Finding Leftover Ingredients at Local Restaurants<br>
우리 동네 음식점에서 남은 식자재 찾기 <br>

&nbsp;&nbsp;&nbsp;코로나의 영향으로 정상적인 영업이 힘들어 남은 식자재로 피해를 보는 소상공인들을 보고 아이디어를 얻어 만든 웹 프로젝트입니다. 음식점 주인들이 자신의 가게를 등록하고 남은 식자재에 대한 판매글을 올리게되면 소비자들은 자신의 동네에 있는 가게와 판매글을 찾을 수 있습니다. <br>
***
## 사용 기술
* 프론트엔드 <br>
   - HTML <br>
   - bootstrap4 <br>
   - ajax <br>
   - javascript <br>

* 백엔드 <br>
  - python-django <br>
  - django REST Framework <br>
***
## 설치

<br>

```python
pip install django
pip install djangorestframework
pip install django-betterforms
```
library가 필요합니다:)<br>
django-betterforms에 발생하는 에러는 관련 파일을<br>
```python
from six import python_2_unicode_compatible
#from django.utils.encoding import python_2_unicode_compatible
from six.moves import reduce
```
로 수정해주시고 pip install six 해주시면 됩니다.<br>
***
## 실행 화면

<br>



![ezgif com-gif-maker (2)](https://user-images.githubusercontent.com/70243735/98221507-0f2a0e00-1f93-11eb-9de2-2bbe3702d814.gif)

***
## 모델 구조
![model_new](https://user-images.githubusercontent.com/70243735/98248933-f896ad80-1fb8-11eb-82c3-17f82ea41b4d.JPG)

***
## 구현 기능
### [ Account App ]
&ensp;: FBV로 구현 <br>
 - [X] 로그인/로그아웃
      - AuthenticationForm를 통한 사용자 인증
      - 사용자의 인증이 올바르지않을 경우 에러페이지
 - [X] 회원가입과 동시에 음식점 등록
      - UserCreationForm을 상속받아 변경후 사용
      - 음식점의 주소는 주소 검색 API로 다음 우편번호 서비스를 이용하여 받습니다.
      
### [ Post App ]
&ensp;: CBV를 통한 요청처리 <br>
&ensp;: HttpTempleteRenderer 사용 <br>
&ensp;: CustomPaginator를 통한 페이징 기능 <br>
 - [X] Create
      - 회원만 가능
 - [X] Read
      - 비회원도 가능
 - [X] Update
      - 작성자만 가능
      - sold out 처리도 가능
 - [X] Delete
      - 작성자만 가능
      - AJAX를 통한 post delete요청
 - [X] 우리 동네 판매글 검색
      - 다음 우편번호 서비스에서 받은 '시/도 + 시/군/구'를 기반으로 검색
 - [X] 제목으로 판매글 검색      
      - ex)'연어'
### [ Store App ]
&ensp;: CBV를 통한 요청처리 <br>
&ensp;: HttpTempleteRenderer 사용 <br>
&ensp;: CustomPaginator를 통한 페이징 기능 <br>
 - [X] 우리 동네 음식점 검색
      - 다음 우편번호 서비스에서 받은 '시/도 + 시/군/구'를 기반으로 검색
 - [X] 음식점 이름으로 음식점 검색  
      - ex)'하남돼지집'
 - [X] 음식점의 개별 페이지
      - 해당 음식점의 소개와 판매글들을 볼 수 있다.
 - [X] 음식점의 좋아요 기능
      - 사용자는 음식점에 좋아요 추천을 할 수 있다. 추천을 많이 받은 음식점이 사용자에게 더 쉽게 노출된다.
***
## 배포
&ensp;: AWS EC2 가상머신으로 배포 환경 구축<br>
&ensp;: Ubuntu 서버를 이용하여 프로젝트 배포<br>
&ensp;프로젝트 링크: http://13.125.254.38/

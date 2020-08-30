#### 게시전후 변경이 필요한 사항정리
##### views> login.ejs
''' <button  class="btn btn-warning" value="카카오가입" name="" onclick="location.href='/auth/kakao/'">카카오로그인<i class="fa fa-btc"></i></button>
<!--AWS <button  class="btn btn-warning" value="카카오가입" name="" onclick="location.href='/auth/kakao/'">카카오가입_단버튼<i class="fa fa-btc"></i></button>--> '''

syntax: [마크다운설명](https://gist.github.com/ihoneymon/652be052a0727ad59601)
atlas MongDB 4.2.8


##PM2사용법
#실행 관리
pm2 start app.js 
pm2 start app.js -- name "servername" >> 프로세스 이름주고 실행기키
pm2 list
pm2 stop 0  >> 프로세스 0번을 멈추기

#프로세스 관리
pm2 stop all >> 모든 프로세스 멈추기
pm2 restart all >> 모든 프로세스 재시작
pm2 reload all >> 모든 프로세스의 다운타임을 0으로 설정후 다시로드
pm2 restart 0 >> 프로세스 0번을 재시작
pm2 delete 0 >> 프로세스 0번을 삭제
pm2 delete all >> 프로세스 전부 삭제
pm2 ping >> pm2가 사용가능한지 핑확인
pm2 updatePM >>pm2 업데이트
pm2 reset <process> >> 리셋 후 메타데이터 리로드

#로그 관리
pm2 logs >>모든 로그 출력
pm2 ilogs >>자세한 로그 출력
pm2 flush >>모든 로그 비우기
pm2 reloadLogs >>로그 다시불러오기



##HTML
&nbsp;  스페이스
&ensp;  스페이스
&emsp;  큰스페이스

##MONGODB
status 가 C 인 사람 중 이름만 가져오겠습니다.
SELECT ename FROM employee WHERE status = 'C' 와 같은 의미 입니다.
db.employee.find({status : "C"}, {ename : 1}) 

{ 필드: { $gt: 값 } }
$gt     //해당 값보다 더 큰 값을 가진 필드를 찾습니다. 숫자 뿐만 아니라 날짜와 ObjectId도 비교할 수 있습니다.

#비교 연산자 쿼리
$lt     //해당 값보다 작은 값을 가진 필드를 찾습니다

$gte    //해당 값보다 크거나 같은 값을 가진 필드를 찾습니다

$lte    //해당 값보다 작거나 같은 값을 가진 필드를 찾습니다

$eq     //해당 값과 일치하는 값을 가진 필드를 찾습니다. 사실 그냥 { 필드: 값 } 하는 것과 같습니다.

$ne     //해당 값과 일치하지 않는 값을 가진 필드를 찾습니다.

{ 필드: { $in: [ 값1, 값2, 값3, ... ] }
$in     //필드의 값이 $in 안에 들어있는 값들 중 하나인 필드를 찾습니다. 아래의 예를 보면 값1, 값2, 값3, ...이 있는데 필드의 값이 그 중 하나면 반환하는 겁니다.

$nin        //필드의 값이 $nin 안에 값들이 아닌 필드를 찾습니다. 아래의 예를 보면 값1, 값2, 값3, ...이 있는데 필드의 값이 그 값들이 아니어야 합니다.

#논리 연산자 쿼리
$or
$or은 여러 개의 조건 중에 적어도 하나를 만족하는 다큐먼트를 찾습니다.

{ $and: [
  { $or: [{ 조건1 }, { 조건2 }] },
  { $or: [{ 조건3 }, { 조건4 }] }
] }
$and        //$and는 여러 개의 조건을 모두 만족하는 다큐먼트를 찾습니다. 조건이 간단하면 그냥 { 필드: 값, 필드: 값 } 이렇게 $and가 없어도 되지만, 주로 다음과 같은 경우 때문에 $and가 필요합니다.


$nor        //$nor은 여러 개의 조건을 모두 만족하지 않는 다큐먼트를 찾습니다. 조건1, 조건2 등등을 모두 만족하지 않아야합니다.

$not        //$not은 뒤의 조건을 만족하지 않는 필드를 찾습니다. $nor의 단일 버전이라고 보시면 됩니다.

$regex:



##NODEJS
==은 같다, !=는 다르다, &&은 and, ||는 or, !은 not과 같은 뜻 

&&의 경우는 앞과 뒤의 조건 모두 true여야 true로 인식하고, || 는 두 조건 중 하나만 true이면 true로 인식합니다. !은 조건의 반대로 인식합니다.



●<%   %> - 스크립트릿, 이 안에 자바 코드 쓸수 있다. 

●<%=   %> - 익스프레션, 자바식 출력

●<%@   %> - 지시자, 웹컨테이너가 jsp 페이지를 처리할 때 필요한 정보를 기술

●<%!    %> - 선언부, 변수선언이나 메서드를 선언

●&{ } - 익스프레션 언어(EL

출처: https://hyunssssss.tistory.com/61 [현's 블로그]






##MONGODB
required:꼭 입력해야 한다.
unique:다른 행과 중복되면 안 된다.
trim:공백을 제거합니다.(문자열 타입에 사용)
default:문서가 생성되면 기본값으로 저장됩니다.
lowercase:대문자를 소문자로 저장한다(문자열 타입)
match:정규식으로 저장하려는 값과 비교한다.
validate:함수로 개발자가 조건을 만듭니다.
set:값을 입력할 때 함수로 조건을 만듭니다.
get:값을 출력할 때 함수로 조건을 만듭니다.
ref:해당하는 모델을 참조할 때 사용한다.

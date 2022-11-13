# Untitle-Study
### fetch 함수로 api 연결하기
- [API 명세서](https://github.com/LeeJoEun-01/wanted-pre-onboarding-challenge-fe-1-api)
- POST 호출
  - 동일한 API를 대상으로 이번에는 새로운 포스팅를 생성하기 위해서 `fetch() 함수`를 사용해보겠습니다. method 옵션을 `POST`로 지정해주고, headers 옵션을 통해 `JSON 포멧`을 사용한다고 알려줘야 하며, 요청 전문을 JSON 포멧으로 직렬화화여 가장 중요한 body 옵션에 설정해줍니다.
- 코드 예시
```javascript
fetch("http://127.0.0.1:8080/users/login", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    email: id,
    password: pwd,
  }),
}).then((response) => response.json())
  .then((data) => {
    console.log(data);
    if(data.details) {
      alert('로그인에 실패하셨습니다. 🥲 아이디랑 비밀번호를 다시 한 번 확인해주세요 🙏🏻')
    } else {
      alert('로그인이 완료되었습니다. 🙌🏻')
    }
  });
```

### input 태그 타입 별 특징
- input 태그 사용 예시
```javascript
<input type="text" id="id" name="id" placeholder="아이디">
```
- Input Type 별 특징
  - password: 필드의 문자는 별표나 동그라 미로 표시로 가려진다.
  - submit: 폼 -헨들러 (form- handler)에게 폼을 제출하 는 버튼을 정의 => 제출 버튼을 누르면 페이지가 새로고침된다.
  - etc ...
- Input 제한 (Restrictions)
  - disabled: Specifies that an input field should be disabled
  - readonly: Specifies that an input field is read only (cannot be changed)
  - size: Specifies the width (in characters) of an input field
  - etc..
  
[참고링크](http://jun.hansung.ac.kr/cwp/htmls/HTML%20Input%20Types.html)

### web Storage
- localStorage: 윈도우나 브라우저 탭을 닫을 경우 데이터가 제거된다.
- sessionStorage: 사용자가 지우지 않는 이상 데이터는 브라우저에 계속 남아있게 된다. (데이터의 영구성)
- 사용방법
```javascript
// localSrorage 부분을 그대로 sessionStorage로 바꿔서 사용

// 키에 데이터 쓰기
localStorage.setItem("key", value);
// 키로 부터 데이터 읽기
localStorage.getItem("key");
// 키의 데이터 삭제
localStorage.removeItem("key");
// 모든 키의 데이터 삭제
localStorage.clear();
// 저장된 키/값 쌍의 개수
localStorage.length;
```

[참고링크](https://www.daleseo.com/js-web-storage/)

### alert에서 `확인` 버튼 클릭 시 이벤트 주기
```javascript
if (window.confirm('Really go to another page?'))
{
    // They clicked Yes
}
else
{
    // They clicked no
}
```
(else 문이 없어도 `취소` 버튼은 생성되며 클릭 시 아무 일도 일어나지 않는다.)
[참고링크](https://stackoverflow.com/questions/9394131/go-to-url-after-ok-button-if-alert-is-pressed/9394143#9394143)

<div align="center">
<h1>Mission02 - 로그인 페이지 구현하기<✔️/h1>
</div>

<br>

### 📌과제 체크리스트
****
- [x] position 실습을 위한 과제 파일은 mission-02/login.html 파일과 mission-02/login.css 파일을 생성 후 각각 마크업과 스타일을 작성한다.
- [x] 마크업 순서는 1. 로그인(제목), 2. 아이디 레이블과 입력서식, 3. 비밀번호 레이블과 입력서식, 4. 로그인 버튼, 5. 회원가입 및 아이디/비밀번호 찾기 링크 순으로 구현한다.
- [x] 이미지 assets 없이 모든 디자인을 CSS로 구현한다. (회원가입 앞에 특수문자는 구현하지 않아도 됨)
- [x] 일부 요소의 배치를 position 속성을 활용하여 구현한다.
- [x] 회원가입, 아이디/비밀번호 찾기 영역은 float을 활용하여 구현한다.
- [x] mission-02/README.md 파일을 생성한 후 마크업 코드와 CSS 코드에 대한 설명을 적고 아래 이미지와 같이 완성된 UI 스크린샷을 삽입한다.


<br>

### 📝 코드 설명
******
#### **1. HTML Mark Up**

```html
 <div class="login">
    <form class="loginForm" action="/" method="post" id="login">
      <h3>로그인</h3>
      <fieldset>
        <legend>로그인 폼</legend>
        <div class="loginForm__group">
          <div class="loginForm__asign">
            <label for="loginForm__id" class="loginForm__id">아이디</label>
            <input type="email" id="loginForm__id" name="loginForm__id" required class="loginForm__id"
              placeholder="euid@euid.de" /><br />
            <label for="loginForm__pw" class="loginForm__pw">비밀번호</label>
            <input type="password" id="loginForm__pw" name="loginForm__pw" required class="loginForm__pw"
              placeholder="8자리 이상" minlength="8"/>
          </div>
          <button type="submit" class="loginButton">로그인</button>
        </div>
      </fieldset>
    </form>
    <span class="line"></span>
    <ul class="login__add">
      <li><a class="login__Join" href="/">회원가입</a></li>
      <li><a class="login__Find" href="/">아이디 비밀번호 찾기</a></li>
    </ul>
  </div>
```
전체 구조를 감싸는 login과 그 내부에 크게 form과 ul로 구성하여 내부 구조 설계하였습니다.
그 안에는 접근성을 위한 fieldset과 legend를 구성하였고 버튼까지 포함하는 loginForm__group과 아이디와 비밀번호 입력 창인 loginForm__asign로 구성되어 있습니다.

#### **2. CSS 설계 - position 사용부분**
- span태그를 고정하기 위한 방법으로 사용
```css
.login{
  width: 244px;
  height: 161px;
  padding: 12px;
  background: linear-gradient(90deg, #ED552F 0%, #E8852E 100%);
  box-shadow: 5px 5px 0px #AAAAAA;
  border-radius: 5px;
  position: relative;
}

span.line{
  width: 209px;
  height: 1px;
  background: #CCCCCC;
  position: absolute;
  left: 18px;
}
```

- 로그인 버튼을 고정하기 위한 방법으로 사용
```css
.loginForm__group {
  width: 220px;
  height: 69px;
  padding: 8px;
  background: #FFFFFF;
  border-radius: 5px 5px 0px 0px;
  border: 0;
  position: relative;
}

.loginButton{
  width: 50px;
  height: 53px;
  font-family: 'Pretendard';
  font-style: normal;
  font-weight: 400;
  font-size: 13px;
  line-height: 150%;
  background: #ED552F;
  border-radius: 5px;
  border: 0;
  color: #FFFFFF;
  position: absolute;
  right: 8px;
  top: 8px;
}
```
#### **3. CSS 설계 - float 사용 부분**
- 회원가입과 아이디 비밀번호 찾기 버튼을 좌우로 배열하는데 사용
```css
.login__add{
  font-family: 'Pretendard';
  font-style: normal;
  font-weight: 400;
  font-size: 13px;
  line-height: 1.5;
  list-style: none  ;
  width: 220px;
  height: 36px;
  background: #FFFFFF;
  border-radius: 0px 0px 5px 5px;
  display: flow-root;
}
.login__Join{
margin: 4px 0 0 16px;
float: left;
}

.login__Find{
  margin:4px 8px 0 0;
  float: right;
}
```


#### **4. 결과 화면**
<img width="260" alt="스크린샷 2023-06-08 오후 10 26 05" src="https://github.com/hanchumon/home-work/assets/116139215/5d9bfad8-5ae3-42d8-9bfb-4bf40cae7d64">


<br>

### 🎁 과제 진행하면서 느낀 점
*** 
#### 2nd 미션 수행 시
- 회고조원들과 코드리뷰를 진행하였는데 리뷰 전보다 다양하게 의견을 나누고 코드에 반영할 수 있어서 효율적으로 코드구성을 할 수 있었다.
- `flex`나 `grid`처럼 레이아웃을 위해 만들어진 옵션은 아니지만 `position`과 `float`으로도 어렵지만 구성은 할 수 있다. 
- HTML 마크업은 하면 할 수록 한계가 없는 느낌이라 힘들지만 한눈에 알아보기 쉽게 만들도록 노력해야겠다.
- `보완해야할 점`
  1. 사파리 폰트 에러 수정할 것! (크롬/파이어폭스 교차검증 완료)
  2. `float`과 `position`에 관련하여 추가 학습 (다양한 옵션 학습)
  



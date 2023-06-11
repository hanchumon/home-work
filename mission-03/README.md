<div align="center">
<h1>Mission03 - 트랜지션 구현하기✔️</h1>
</div>

<br>

### 📌과제 체크리스트
****
- [x] transition 실습을 위한 과제 파일은 mission-03/transition.html 파일과 mission-03/transition.css 파일을 생성 후 각각 마크업과 스타일을 작성한다.
- [x] 관련 사이트는 제목으로 각각 항목은 링크로 구현한다.
- [x] 링크 목록은 5개이며 CSS를 사용하여 화면에 1개의 목록만 보이도록 구현한다.
- [x] 목록에 마우스를 올리면 5개의 목록이 펼쳐지도록 구현한다.
- [x] transition 속성을 활용하여 애니메이션 효과를 적용한다.
- [x] mission-03/README.md 파일을 생성한 후 마크업 코드와 CSS 코드에 대한 설명을 적고 아래 이미지와 같이 완성된 UI 스크린샷을 삽입한다.


<br>

### 📝 코드 설명
******
#### **1. HTML Mark Up**

```html
  <div class="site">
    <h2 class="site-title">
      <span class="site-title-1">관련</span>
      <span class="site-title-2">사이트</span>
    </h2>
    <ul class="site-list">
      <li><a href="/">제로베이스</a></li>
      <li><a href="/">W3C</a></li>
      <li><a href="/">데이원 컴퍼니</a></li>
      <li><a href="/">웹접근성 연구소</a></li>
      <li><a href="/">MDN</a></li>
    </ul>
  </div>
```
전체 구조를 감싸는 site와 그 내부에 제목 태그와 ul로 구성하여 내부 구조를 간단하게 설계하였습니다.

#### **2. CSS 설계 - transition 사용 부분**
- `hover` 하였을 때 화면을 확장하기 위해 전체를 감싸는 `.site`에 `hover` 속성을 적용하였습니다. 또 내부에 있는 흰색 화면도 동시에 동작 해주기 위해 .`site:hover`과 `site-list`를 동시에 적용하여 한꺼번에 작동하게 처리하였습니다. 내부에 링크는 화면이 펼쳐진 후 내려오게 하기 위하여 `500ms`의 딜레이를 주었습니다.
```css
.site:hover{
  height: 222px;
  transition: height 1s ease-out;

}
.site:hover .site-list {
  height: 165px;
  padding-top: 20px;
  transition: padding-top 1s ease-in-out 500ms, height 1s ease-out;
}

```

#### **3. 결과 화면**
![GIFMaker_me](https://github.com/hanchumon/home-work/assets/116139215/3ec46828-2157-48ea-b379-6269cb4d81f2)


<br>

### 🎁 과제 진행하면서 느낀 점
*** 
#### 3rd 미션 수행 시
- `CSS` 구성 후 `validation Test`를 진행해 보았는데 화면 구성은 되지만 문법적 오류가 몇가지 발견되어서 수정하면서 역시 `CSS`는 눈에보이는게 전부가 아니라는 생각을 하게 되었습니다.
- `transition`은 간단해보이지만 드라마틱한 효과를 줄 수 있는 기법인 것 같아서 잘 활용하면 좋을 것 같습니다.
- `보완해야할 점`
  1. 돌아올 때 천천히 돌아오게 하는 법 고민하기!

  



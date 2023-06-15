<div align="center">
<h1>Mission05 - sprite 활용하기✔️</h1>
</div>

<br>

### 📌과제 체크리스트
****
- [x] sprite 실습을 위한 과제 파일은 mission-05/sprite.html 파일과 mission-05/sprite.css 파일을 생성 후 각각 마크업과 스타일을 작성한다.
- [x] 더보기 링크 앞에 플러스 기호는 생략해도 무방하다.
- [x] rank.png(webcafe-RWD/assets 폴더에 있음) 이미지를 활용하여 스프라이트 기법으로 스타일링 한다.
- [x] 각 인기 사이트의 순위를 나타내는 영역은 기존 `<ol>` 요소에서 제공하는 기본 숫자를 보이지 않도록 한 후 CSS로 구현한다.
- [x] mission-05/README.md 파일을 생성한 후 마크업 코드와 CSS 코드에 대한 설명을 적고 아래 이미지와 같이 완성된 UI 스크린샷을 삽입한다.


<br>

### 📝 코드 설명
******
#### **1. HTML Mark Up**

```html
  <section class="favorite">
    <h2 class="favorite-title">인기 <span class="accent-color">사이트</span></h2>
    <ol class="favorite-list">
      <li class="favorite-list-item sprite__up">W3C</li>
      <li class="favorite-list-item sprite__down">Web Standards</li>
      <li class="favorite-list-item sprite__none">CSS ZenGarden</li>
      <li class="favorite-list-item sprite__up">MDN</li>
    </ol>
    <a href="/" class="favorite-more"><span class="fa-icon fa-sharp fa-solid fa-plus"></span>더보기</a>
  </section>
```
전체 구조를 감싸는 sectionrhk 그 내부에 제목 태그와 ol로 구성하여 내부 구조를 간단하게 설계하였습니다.

#### **2. CSS 설계 - `ol` `list-style` 부분**
- `ol` tag에는 직접적으로 디자인 할 수 없기 때문에 가상 요소인 `::before`을 이용하여 디자인 하였습니다. 앞쪽에 숫자를 입력하기 위하여 `couter-increment`와 `counter()`를 사용하였는데 `counter-increment`를 이용하여 변수를 지정하고 `counter()` 함수에 담아서 사용하였습니다.
```css
.favorite-list-item{
  margin: 8px 0;
  counter-increment: number;
}

.favorite-list-item::before{
  content: counter(number);
  width: 20px;
  height: 20px;
  border-radius: 5px;
  background: #A3A3A3;;
  color: #fff;
  display: inline-block;
  text-align: center;
  margin-right: 5px;
  font-size: 14px
}

```
#### **3. CSS 설계 - `ol` `list-style` 부분**
- 가상요소인 `::after`을 이용하여 `sprite`이미지를 `background`에 적용하여 `background-position`을 조절하여 사용하였습니다. 배치는 `float`를 사용하여 우측에 배치하였고, 시안과 위치를 맞추기 위해 `margin-right`를 음수를 주어 설정하였습니다.
```css
.sprite__up::after{
  content: "";
  background: url(./rank.png) no-repeat;
  width: 20px;
  height: 20px;
  float: right;
  margin-right: -10px;
  background-position: 0 4px;
}

.sprite__none::after{
  content: "";
  background: url(./rank.png) no-repeat;
  width: 20px;
  height: 20px;
  float: right;
  margin-right: -10px;
  background-position: 0 -17px;
}

.sprite__down::after {
  content: "";
  background: url(./rank.png) no-repeat;
  width: 20px;
  height: 20px;
  float: right;
  margin-right: -10px;
  background-position: 0 -40px;
}

```

#### **4. 결과 화면**
<img width="228" alt="스크린샷 2023-06-15 오후 10 28 01" src="https://github.com/hanchumon/home-work/assets/116139215/fdaf71b4-e344-4c0d-84fb-7c216408c719">



<br>

### 🎁 과제 진행하면서 느낀 점
*** 
#### 5th 미션 수행 시
- `sprite` 이미지를 사용하여 이미지를 렌더링해 보니 이미지 하나로 여러개를 조절할 수 있는 점이 유용해 보였다.
- 가상요소를 사용하는 점이 생각보다 쉽지 않아서 가상요소와 관련된 부분을 추가로 학습해야겠다고 생각했습니다.
- `보완해야할 점`
  1. `sprite` 부분 한번에 묶어서 코드정리하기(속성 선택자 사용하기)!
  2.  다양한 리스트 태그들을 만들고 디자인해보기

  



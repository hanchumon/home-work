<div align="center">
<h1>Mission04 - GRID를 이용하여 레이아웃 구현하기✔️</h1>
</div>

<br>

### 📌과제 체크리스트
****
- [x] grid 실습을 위한 과제 파일은 mission-04/grid.html 파일과 mission-04/grid.css 파일을 생성 후 각각 마크업과 스타일을 작성한다.
- [x] 더보기 링크 앞에 플러스 기호는 생략해도 무방하다.
- [x] 링크 목록은 5개이며 CSS를 사용하여 화면에 1개의 목록만 보이도록 구현한다.
- [x] 이미지는 “W3C 리뉴얼”이라는 캡션 위에 썸네일 이미지를 사용한다.
(해당 이미지는 배경으로 지정하지 말고 <img> 요소를 사용하여 콘텐츠 이미지로 배치)
- [x] grid를 활용하여 레이아웃을 구현한다.
- [x] mission-04/README.md 파일을 생성한 후 마크업 코드와 CSS 코드에 대한 설명을 적고 아래 이미지와 같이 완성된 UI 스크린샷을 삽입한다.


<br>

### 📝 코드 설명
******
#### **1. HTML Mark Up**

```html
  <section class="news">
    <h2 class="news-title">새소식</h2>
    <span class="line_decoration"></span>
    <p class="news-sub-title">W3C 사이트가 리뉴얼 되었습니다.</p>
    <p class="news-time">
      <time datetime="2022-07-18">2022.07.18</time>
    </p>
    <p class="news-contents">
      디자인 및 다양한 view 환경을 고려하여 구성되어 있으며, 기존보다 최신 정보 및 개발자를 위한 기술 가이드도 찾기 쉽도록 구성되어 있습니다.
    </p>
    <figure class="news-figure">
      <img src="./news_1.png" alt="W3C 리뉴얼 화면" class="new-image" />
      <figcaption>W3C 리뉴얼</figcaption>
    </figure>
    <a href="/" class="news-more">더보기</a>
  </section>
```

- body
  - section.news
    - h2.news-title
    - span.line_decoration
    - p.news-sub-title
    - p.news-time
      - time[datetime="2022-07-18"]
    - p.news-contents
    - figure.news-figure
      - img.new-image[src="./news_1.png"][alt="W3C 리뉴얼 화면"]
      - figcaption
    - a.news-more[href="/"]


전체 section을 구성 한 뒤 같은 레벨에 자식요소를 구성하여 시맨틱 요소를 해치 지 않는 선에서 마크업 한다.


#### **2. CSS 설계 - 각 파트별 `grid area` 값 부여**
- `grid-template-areas`를 사용하기 위해 파트별`grid-area`를 사용하여 구성
```css
.news-title{
  grid-area: title;
}

.news-time {
  grid-area: time;
}

.line_decoration{
  grid-area: line;
}

.news-sub-title{
  grid-area: subtitle;
}

.news-time {
  grid-area: time;
}

.news-contents{
  grid-area: contents;
}

.news-figure{
grid-area: figure;
}

.news-more{
  grid-area: more;
}
```

#### **3. CSS 설계 - 전체 섹션 부분에 `grid` 적용 및 `grid` 구성**
- `grid template`를 사용하여 각 부분의 사이즈 설계 및 `grid-area`를 사용하여 구성
```css
.news{
  width: 380px;
  height: 200px;
  display: grid;
  grid-template-columns: 122px 1fr 1fr;
  grid-template-rows: 21px 24px 21px  21px 1fr;
  grid-template-areas: 
  "title title more"
  "line line line"
  "figure subtitle subtitle"
  "figure time time"
  "figure contents contents"
  ;
  row-gap: 4px;
}

```


#### **4. 결과 화면**
![mission-04](https://github.com/hanchumon/home-work/assets/116139215/abc5d2b4-95c0-46f9-96c5-f1561a78f9a8)



<br>

### 🎁 과제 진행하면서 느낀 점
*** 
#### 4th 미션 수행 시
- `Grid` 구성 후 바로 아래 자식요소에만 `Grid` 적용 가능하다는 것을 잊지말 것!
- `Grid`를 사용하면 마크업 순서와 상관없이 구성할 수 있는 메리트가 있다.

- `보완해야할 점`
  1. Layout을 위해 margin값으로 조정했는데 다른 더 좋은 방법이 있는지 고민하기!

  



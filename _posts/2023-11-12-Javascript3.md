---
layout: single
title: "Javascript : 기본연습3"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: javascript
sidebar:
  nav: "counts"
---

<br>

# <span style="color:#9336b5">data-category</span>, <span style="color:#e6ca9a">data-type</span> 속성을 직접 작성하고 Javascript로 동작을 구현

<div class="notice--info">
다음은 장르에 맞는 버튼을 클릭하면 그에 맞는 이미지가 노출되는 것을 만들기 위해 작성한 html 코드다.
또한 알맞는 장르 선택 시 genre--selected 요소가 따라서 추가되도록 만들 것임.
</div>

```html
<ul class="genres">
  <li>
    <button class="genre genre--selected" data-category="all">전체</button>
  </li>
  <li>
    <button class="genre" data-category="action">액션</button>
  </li>
  <li>
    <button class="genre" data-category="comedy">코미디</button>
  </li>
  <li>
    <button class="genre" data-category="horror">공포</button>
  </li>
</ul>

<ul class="movies">
  <li class="movie" data-type="action">
    <img src="images/movie1.jpg" class="movie__img">
  </li>
  <li class="movie" data-type="comedy">
    <img src="images/movie2.jpg" class="movie__img">
  </li>
  <li class="movie" data-type="horror">
    <img src="images/movie3.jpg" class="movie__img">
  </li>
</ul>
```

<hr>
<br>

<div class="notice--info">
클릭한 요소의 data-category 값을 movies 목록에 있는 data-type 값과 일치하는 것끼리 매칭한다.
즉 필터링에 관한 것임. 사용할 속성을 잘 익혀두자.
</div>

<div class="notice--info">
서로 매칭되는 속성 값이 없을 경우 함수를 빠져나오는 로직도 추가. (filter가 NULL일 때!)
</div>

```javascript
const genresSelection = document.querySelector('.genres');
const genres = document.querySelectorAll('.genre');
const moviesContainer = document.querySelector('.movies');

genresSelection.addEventListener('click', e => {
  const filter = e.target.dataset.category;
  if(filter == null) {
    return;
  }
  handleActiveClass(e.target);
  filterMovies(filter);
});

//가독성을 위해 함수로 만들어 사용하기.
//genre--selected 클래스 추가
const handleActiveClass = (target) => {
  const active = document.querySelector('.genre--selected');
  active.classList.remove('.genre--selected');
  target.classList.add('.genre--selected');
};

//필터링 작업
const filterMovies = (filter) => {
  moviesContainer.forEach(movie => {
    if(filter === 'all' || filter === movie.dataset.type) {
      movie.style.display = 'block';
    } else {
      movie.style.display = 'none'
    }
  });
};
```
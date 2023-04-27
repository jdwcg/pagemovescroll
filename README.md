링크 클릭시 페이지 이동 후 해당 위치로 스크롤 되게 하기

page_link.html에
아이디를 부여한 링크를 만듭니다.

<a href="./scroll_offset.html#section1">섹션1</a>
<a href="./scroll_offset.html#section2">섹션2</a>
<a href="./scroll_offset.html#section3">섹션3</a>

scroll_offset.html으로 가서 스크립트를 작성합니다.

window.onload = function () {
  var currentUrl = window.location.href;
  // 현재 url
  var urlWithoutHash =
    location.origin + location.pathname + location.search;
  console.log(urlWithoutHash);
  // # 이후의 문자열을 제외한 URL 출력

  console.log(currentUrl);
  var hash = window.location.hash;

  console.log(urlWithoutHash + hash);

  if (currentUrl == urlWithoutHash + "#section1") {
    let section1 = document.querySelector("#section1");
    window.scroll({ top: section1.offsetTop - 100, behavior: "smooth" });
  } else if (currentUrl == urlWithoutHash + "#section2") {
    let section2 = document.querySelector("#section2");
    window.scroll({ top: section2.offsetTop - 100, behavior: "smooth" });
  } else if (currentUrl == urlWithoutHash + "#section3") {
    let section3 = document.querySelector("#section3");
    window.scroll({ top: section3.offsetTop - 100, behavior: "smooth" });
  }
};

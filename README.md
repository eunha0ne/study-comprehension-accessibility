# 웹 접근성

## 웹 접근성의 이해
* **Web accessibility(웹 접근성)이란?**
  * **장애를 가진 사람과 장애를 가지지 않은 사람 모두가 웹사이트를 이용할 수 있게 하는 방식을 가리킨다.** 사이트가 올바르게 설계되어 개발되고 편집되어 있을 때 모든 사용자들은 정보와 기능에 동등하게 접근할 수 있다.

> 접근에 대한 개념의 다양성으로 인한 인식의 부족보다는 접근성에 대한 개념을 잘못 이해하고 있는 것이 더 욱 문제이다. 즉, 접근성을 단지 장애인에게 국한된 문제라고 잘못 이해하고 있는 경우가 대부분이라는 것이다. 비록 접근성 준수가 장애인에게 가장 혜택이 많이 돌아가는 것은 사실이지만, 접근성이란 장애인뿐만 아니라 모든 사람이 정보통신 기기나 서비스를 손쉽게 활용할 수 있도록 만드는 것을 말하는 것이다.

* **"웹의 힘은 그 광범위함에 있다. 장애에 구애없이 모든 사람이 접근할 수 있다는 것이 웹의 본질적인 면이다."** - 팀 버너스 리
  * The power of the Web is in its universality, Access by everyone regardless of disability is an essential aspect.

* 장애란?
  * 어떤 사물의 진행을 가로막아 거치적거리게 하거나 충분한 기능을 하지 못하게 하는 것 또는 그런 일
  * 두 번재 신체 기관이 제 기능을 하지 못하거나 정신 능력에 결함이 있는 상태

* 장애 환경
  * 전맹 시각 장애: 시력이 거의 없어 앞을 볼 수 없음. 다른 감각으로 웹을 이용
  * 저시력 시각 장애: 일상적인 생활이 어려운 정도, 좀 더 크고 선명하게 볼 수 있는 기능 필요
  * 중증 운동 장애: 손과 팔을 사용하지 못하고, 보조기기이 도움이 필요
  * 손 운동 장애: 한 손만 가능, 정교한 조작이 어려움
  * 청각 장애: 안내 문구나 자막과 같은 화면의 문자에 의존
  * 맥 사용자: 윈도우에서만 사용이 가능한 경우
  * 느린 인터넷: 인터넷 환경이 열악한 경우, 로딩 속도가 웹 페이지를 인식하는데 불편하게 만듬

## 웹 접근성 지침 소개
* WCAG: Web Content Accessibility Guidelines
  * W3C에서 발표한 웹 콘텐츠 접근성 지침
* KWCAG: Korean Web Content Accessibility Guidelines
  * 해외 웹 표준 기술 동향을 기준으로 국내 실정에 맞게 반영된 웹 접근성 지침

### 적절한 대체 텍스트 제공
* alt 속성
```html
<img src="160314.png" alt="주식수수료 평생무료 비대면계좌개설 신규/온라인/유관기관 제비용 제외 2018년 12월 31일까지 선물/옵션 1년 무료, 신용이자 연 3.5% 60일 우대">
```

버튼과 같은 `의미 있는 이미지`의 경우에도 대체 텍스트를 시각적으로 보는 것과 동등하게 제공
```html
<img src="btn_next.png" alt="다음 콘텐츠 보기">
<img src="brown_img_5.png" alt="미안해하는 브라운">
<a href="http://www.naver.com">
  <img src="qr_code.png" alt="http://www.naver.com 바로 가기 QR코드">
</a>
<img src="text.jpg" alt="보안 문자">
```

* 마크업
```html
<img src="160314.png" alt="">
<p class="blind">
  주식수수료 평생무료 비대면계좌개설 신규/온라인/유관기관 제비용 제외  
  2018년 12월 31일까지 선물/옵션 1년 무료, 신용이자 연 3.5% 60일 우대
</p>
```
이미지 테그와 대체 텍스트로 사용하고 있는 P 테그에 동일한 **내용이 중복되면 스크린리더에서 같은 내용을 반복해서 전달하게 됨으로 이미지 테그의 알트는 비워둔다.** 단, alt 속성을 완전히 지울 경우. src에 입력된 파일명을 읽기 때문에 알트 속성을 비운 상태로 사용한다.

```html
<a href="…">
  <img src="thumb01.jpg" alt="">
  <span>웨딩 사진을 모티브로 만든 도일리 #프랑스자수</span>
</a>
```

* 데이터 차트나 복잡한 콘텐츠
```html
<img src="graph.png" alt="" />
<table class="blind">
    <caption>...</caption>
        <thead>
	 <tr>
	    <th scope="col">년도</th>
	    <th scope="col">학과</th>
	    <th scope="col">지원 수</th>
	</tr>
    </thead>
    <tbody>
       <tr>
           <td>2003</td>
           <td>언어학</td>
           <td>10200명</td>
       </tr>
     ...
    </tbody>
</table>
```

* 사용자가 업로드하는 이미지
이미지 업로드 시에, 사용자가 대체 텍스트로 입력한 내용이 실제로 대체 텍스트로 제공되도록 구현

## References
* [웹 접근성 연구소](https://www.wah.or.kr:444/Accessibility/define.asp)
* [웹 접근성의 이해, 이선주](https://www.edwith.org/web-accessibility/lecture/46005/)
* [제 7회 널리 세미나](/)
* [위키백과](https://en.wikipedia.org/wiki/Web_accessibility)

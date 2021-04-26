# 3. Understandable
정보와 UI 조작은 이해할 수 있어야 한다.

## 3.1 Readable
텍스트 콘텐츠를 읽을 수 있고 이해할 수 있게 만든다.

### 3.1.1 Language of Page
>(Level A) 각 웹 페이지의 기본 언어를 프로그래밍 방식으로 확인할 수 있다.

목적
+ 이는 텍스트 및 기타 언어적 컨텐츠가 올바르게 랜더링되어야함을 의미한다. 
+ 그래야 시각적 브라우저에 문자와 스크립트가 올바르게 표시될 수 있다. 
+ 스크린 리더 사용 시, 컨텐츠를 올바르게 발음하여 제공할 수 있다. 
+ 미디어 플레이어의 경우 자막을 올바르게 표시할 수 있다.

이점  
아래와 같은 사람들이 콘텐츠를 더 잘 이해할 수 있다.
+ 텍스트를 음성으로 변환하는 스크린 리더 혹은 다른 기술을 사용하는 사람들
+ 문자를 인식하거나 단어를 해독하는 것과 같이 유창하고 정확하게 작성된 자료를 읽는 것이 어렵다고 느끼는 사람들
+ 텍스트 음성 변환 소프트웨어를 사용하는 특정인지, 언어 및 학습 장애가 있는 사람들
+ 1.2.4 Caption에서 동기화된 미디어에 포함된 모든 라이브 오디오 콘텐츠에 자막을 제공해야함을 정의하는데, 동기화 된 미디어를 위해 자막에 의존하는 사람들 

적용 방법  
&lt;html&gt; 요소 내에서 lang 속성을 사용하여 웹 페이지의 기본 언어를 식별할 수 있도록 할 수 있다.
해당 웹 페이지가 영어로 작성되어 있다면, 
```html
<html lang="en">
```
과 같이 작성해주어야 한다.
두 가지 이상의 언어로 구성된 웹 페이지의 경우, 대부분의 내용이나 주된 컨텐츠의 언어를 따른다.

사례  
+ [Google](www.google.co.kr)에 &lt;html lang="ko"&gt;가 적용되어 있는 모습
    ![3.1.1 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_1_1_ex01.PNG)

### 3.1.2 Language of Parts
> (Level AA) 고유명사, 기술 용어, 알 수 없는 언어의 단어, 주변 텍스트의 언어에 포함된 단어나 구절을 제외하고, 콘텐츠에 포함된 각 구절의 언어를 프로그래밍 방식으로 확인할 수 있다.

목적  
+ 이는 사용자 에이전트 여러 언어로 작성된 콘텐츠를 올바르게 표시할 수 있도록 해야함을 의미한다.
+ 그래야 사용자 에이전트나 다른 보조 기술이 해당 언어의 표현 및 발음 규칙에 따라 콘텐츠를 표현할 수 있다.
+ 사용자 에이전트나 스크린 리더, 점자 화면 및 기타 음성 브라우저에서 텍스트의 각 구절의 언어가 식별되면 텍스트를 더 정확하게 렌더링 할 수 있다.
+ 스크린 리더는 텍스트 언어의 발음 규칙을 표시할 수 있다.
+ 시각적 브라우저도 왼쪽에서 오른쪽으로 읽는 언어와 반대로 읽는 언어 사이를 전환하거나 텍스트가 다른 문자를 사용하는 언어로 렌더링될 때에도 적절한 방식으로 문자와 스크립트를 표시할 수 있다.

이점  
아래와 같은 사람들이 콘텐츠를 더 잘 이해할 수 있다.
+ 텍스트를 합성 음성으로 변환하는 화면 판독기 또는 기타 기술을 사용하는 사람들
+ 문자와 알파벳을 인식하고, 단어를 해독하고, 단어와 구를 이해하는 것과 같이 유창하고 정확하게 작성된 자료를 읽는 것이 어렵다고 생각하는 사람들
+ 텍스트 음성 변환 소프트웨어를 사용하는 특정 인지, 언어 혹은 학습에 어려움이 있는 사람들
+ 동기화된 미디어 콘텐츠의 사운드 트랙에서 언어 변경을 인식하기 위해 자막에 의존하는 사람들

적용방법  
lang 속성을 부분적으로 이용하여 적절한 컨텐츠의 언어로 식별할 수 있다.
```html
<blockquote cite = "John F. Kennedy" lang = "de">
     <p>Ich bin ein Berliner</p>
 </blockquote>
```
```html
<p>The only French phrase I know is <span lang = “fr”>je ne sais quoi</code>.</p>
```
와 같이 &lt;blockquote&gt; 나 &lt;span&gt; 요소에 lang 속성으로 값을 주어 인용구나 흔하지 않은 외래어, 구절을 올바르게 렌더링 할 수 있다.

사례
+ [네이버 오늘의 영어 회화](https://learn.dict.naver.com/conversation#/endic/20210424)에서 다른 부분은 lang="ko" 이지만 오늘의 영어 회화의 영어 문장 부분은 span 요소에 data-lang = "en"과 같이 data-lang 속성을 이용해 영어임을 표시하는 모습
    ![3.1.2 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_1_2_ex01.png)

### 3.1.3 Unusual Words
> (Level AAA) 관용구와 전문 용어 등, 보편적이지 않거나 제한된 방식으로 사용된 단어나 구절의 구체적인 정의를 확인하기 위한 메커니즘을 이용할 수 있다.


목적
+ 이는 비문이나 전문 용어 이해 및 사용을 어렵게 하는 특정 장애나 비유적인 언어 이해 및 사용을 어렵게 하는 특정 장애를 고려해야함을 의미한다.
+ 비전문가를 위한 전문적인 내용도 이 기준을 충족시키는 것을 권장한다.

이점  
아래와 같이 인지 및 언어, 학습 장애가 있는 사람들에게 도움이 될 수 있다.
+ 단어를 해독하기 어려운 사람들
+ 단어와 구절을 이해하기 어려운 사람들
+ 맥락을 통해 이해하는 데 어려움이 있는 사람들 
아래와 같이 시각 장애가 있는 사람들에게도 도움이 될 수 있다.
+ 화면 돋보기를 사용하여 확대했을 때, 맥락을 찾지 사람들

적용방법  
html 태그를 사용할 필요없이, 일반적이지 않다고 판된되는 단어를 사용할 때는 그 단어의 정의를 그 단어가 사용되기 직전 혹은 직후에 텍스트로 제공하는 방법이 있다.
```
그는 소리가 행성 간 공간을 채우는 물질로 생각되는 에테르를 통해 이동한다고 믿었습니다.
```
```
프린터 드라이버를 업데이트해야 할 수도 있습니다 (드라이버는 프린터에 대한 특정 지침이 포함 된 소프트웨어입니다).
```


&lt;dl&gt;, &lt;dt&gt;, &lt;dd&gt; 요소를 사용해 단어와 단어의 의미를 하나의 그룹으로 묶고, 목록으로 표시하여 시각적으로 단어와 단어의 의미를 나타내는 문장이 떨어지더라도 두 요소가 연관되어 있도록 할 수도 있다.
```html
<dl title="Nautical terms">
  <dt>Knot</dt>
  <dd>
    <p>A <em>knot</em> is a unit of speed equaling 1 
      nautical mile per hour (1.15 miles per hour or 1.852 
      kilometers per hour).</p>
  </dd>
  <dt>Port</dt>
  <dd>
    <p><em>Port</em> is the nautical term (used on 
      boats and ships) that refers to the left side
      of a ship, as perceived by a person facing towards 
      the bow (the front of the vessel).</p>
  </dd>
</dl>     
```
&lt;link&gt; 태그나 &lt;a&gt; 태그를 이용하여 해당 단어의 의미가 정리된 단어의 모음집 혹은 해당 단어의 정의를 찾기 위한 온라인 사전에 대한 링크를 참조할 수도 있다.
```html
<link rel="glossary" href="https://www.w3.org/TR/WCAG20/#glossary">
```

&lt;dfn&gt; 태그를 이용하여 용어의 정의를 나타낼 수 있다. &lt;dfn&gt;은 가장 가까운 조상 요소 중 &lt;p&gt; 혹은 &lt;dt&gt;, &lt;dd&gt; 쌍 혹은 &lt;section&gt;을 용어의 정의로 간주한다.
```html
The following code snippet demonstrates the use of the dfn element.

<p>The Web Content Accessibility Guidelines require that non-text content
has a text alternative. <dfn>Non-text content</dfn> is content that is not a sequence
of characters that can be programmatically determined or where the sequence is
not expressing something in human language;
</p> 
```

사례  
+ [G-health 공공보건 포털의 희귀질환자 의료비 지원사업 게시글](https://www.g-health.kr/portal/bbs/selectBoardArticle.do?bbsId=U00322&nttId=381807&menuNo=200448&lang=&searchCndSj=&searchCndCt=&searchWrd=&pageIndex=1&vType=Z2)에서 희귀질환자 의료비 지원 사업을 이용할 수 있는 사람들의 조건을 &lt;dl&gt;, &lt;dt&gt;, &lt;dd&gt; 요소를 사용해 건강보험가입자가 이용할 수 있다면, 그 건강보험가입자가 무엇을 의미하는 지 등을 설명하여 각 단어의 뜻을 명확히 표현한다.
    ![3.1.3 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_1_3_ex01.png)

### 3.1.4 Abbreviations
>(Level AAA) 약어의 확장된 형태나 의미를 확인하는 매커니즘을 이용할 수 있다.

목적
+ 이는 사용자가 약어의 확장된 형태에 접근할 수 있어야함을 의미한다.
+ 약어는 일반 단어처럼 보이지 않으며 일반적인 언어 규칙에 따라 발음할 수 없으며
+ 때로는 동일한 약어가 다른 맥락에서 다르게 해석되기도 하고
+ 일부 약어는 일반적인 단어처럼 보이지만 철자가 다르거나, 
+ 일반적인 단어와 철자가 같지만 다른 방식으로 사용이 되기도 하므로
+ 약어는 약어임을 나타나며, 해당 약어의 확장된 형태가 제공되어야 한다.

이점  
아래와 같은 사람들이 콘텐츠를 더 잘 이해할 수 있다.
+ 단어를 해독하는 데 어려움이 있는 사람들
+ 화면 돋보기에 의존하여 확대 시 상황에 맞는 단서가 줄어드는 사람들
+ 기억력에 제한이 있는 사람들
+ 맥락을 통해 이해하는 데 어려움이 있는 사람들 
  
적용방법  
웹 페이지 내에서 처음 해당 약어가 발생했을 때, 해당 약어와 해당 약어의 확장된 형태를 함께 제공하는 방법이 있다.
```
"유엔 인권 최고ㄷ 대표 사무소 (UNHCR)는 난민을 보호하고 지원하기 위해 1950년에 설립되었습니다."

"WAI(Web Accessibility Initiative)는 접근성에 대한 W3C의 노력을 보여줍니다.
```
위와 같이 괄호를 사용해 나타내는 것이 일반적이다.

&lt;link&gt; 태그나 &lt;a&gt; 태그를 이용하여 해당 약어의 의미가 정리된 약어의 모음집 혹은 해당 약어의 정의를 찾기 위한 온라인 사전에 대한 링크를 참조할 수도 있다.
```html
<p> ... <a href="#definition"> さ じ を 投 げ る </a> ... </p>
<h3> 脚注 : </h3>
<dl>
<dt id = "definition"name = "definition"> さ じ を 投 げ る </dt>
<dd> ど う す る こ と も で き な く な り 、 あ き ら め る こ と。 </dd>
</dl>
```

&lt;abbr&gt; 태그를 사용하여 약어를 확정, 정의할 수 있다.
```html
 <p>The use of <abbr title="Keep It Simple Stupid">KISS</abbr> became popular in ...</p>        
```

사례
+ [위키피디아](https://en.wikipedia.org/wiki/World_Wide_Web)에서 V, T, E라고 임의로 정한 약어를 사용할 때 &lt;abbr&gt; 태그를 이용하여 V가 vies this template, T가 Discuss this template, E가 Edit this template의 의미로 사용되었음을 알려주고 있다. 마우스 커서를 가져다 댔을 때 title 속성에 의해 의미가 보여지며 스크린 리더를 사용했을 때도 약어의 의미를 알 수 있다. 
    ![3.1.4 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_1_4_ex01.png)

### 3.1.5 Reading Level
> (Level AAA) 고유명사와 제목을 제외하고 텍스트를 이해하는 데 중등 교육(중학교) 수준 이상의 독해력이 필요한 경우 이를 보완하는 콘텐츠 또는 그러한 독해력이 필요하지 않은 버전을 이용할 수 있다.

목적  
+ 이는 난독증과 같은 읽기 장애가 있어도 최대한 글을 이해할 수 있도록 단어의 수준이나 가독성 등을 고려해야함을 의미한다.
+ 필요에 따라서 이해를 돕기 위한 추가 콘텐츠를 사용할 수 있어야하며, 이러한 추가 콘텐츠가 필요한 지를 판단할 수 있는 테스트를 설정해야한다.
+ 복잡한 연구 논문을 읽기 쉽게 요약한 과학 저널이나, 일반인을 위한 의료 정보, 중동 교육 수준으로 읽을 수 있는 정도의 필요한 과학정보, e-러닝 애플리케이션 등에 적용할 수 있다.

이점  
아래와 같은 사람들이 콘텐츠를 더 잘 이해할 수 있다.
+ 일반 지식이나 특정 정보를 얻기 위해 기사, 지시사항, 텍스트나 점자로 이루어진 신문 등의 글로 된 언어를 이해하고 해석하는 데 어려움이 있는 사람들 

적용방법    
보고서에 차트와 그래프를 포함하는 것이나 제품에 대한 온라인 설명서에 단계별 지침을 시각적인 모양으로 보여주는 사진으로 설명하고, 쓰나미에 대해 설명하는 글에 쓰나미의 발생과정과 퍼지는 과정을 애니메이션으로 함께 제공하는 등의 방법이 있다.  
  
어려운 내용이라면 전체 내용 전에 전문 용어 대신 가독성 공식이 적용된 평균 길이가 16단어인 문장들로 요약 항목을 제공할 수도 있다.
  
또한, 청각 장애가 있거나 특정 인지, 언어에 어려움이 있어 수화가 더 이해하기 쉬울 수 있기 때문에 텍스트와 함께 수화 콘텐츠를 추가로 제공할 수도 있다.
  
제일 좋은 방법은, 웹 페이지의 텍스트를 읽기 어렵지 않게 작성하는 것이다. 텍스트에 중등 교육 수준보다 더 높은 수준의 읽기 능력이 필요하지 않은 경우, 대부분 보충자료나 대체자료가 필요하지 않다. 따라서 텍스트의 복잡성을 줄이기 위한 여러 기술을 적용할 수 있다.

사례  
+ [우리은행 웹접근성 안내](https://spot.wooribank.com/pot/Dream?withyou=CQIBG0050)를 보면 센스리더 설치 및 설정 안내부터 음성출력 속도 조절하기, 가상 커서 설정하기 등의 도움말에 이해를 돕는 추가적인 스크린샷 이미지를 제공한다. 또한 짧고 정확한 문장으로 각 단계를 설명하고 있으며 각 단계에 번호를 부여하여 텍스트를 읽기 쉽게 작성한 것을 볼 수 있다.
    ![3.1.5 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_1_5_ex01.png)

### 3.1.6 Pronunciation
>(Level AAA) 발음을 모르면 문맥에서 단어의 의미가 모호한 경우 단어의 구체적인 발음을 확인하는 매커니즘을 이용할 수 있다.

목적
+ 이는 시각 장애가 있는 사람, 읽기 장애가 있는 사람 등 의미 파악을 발음에 의존하는 경우에도 콘텐츠를 이해할 수 있도록 해야함을 의미한다.
+ 종종 단어나 문자는 발음에 따라 다른 의미를 가지기도 하기 때문에 어떤 의미로 쓰인 것인지 발음 정보를 주어야한다.
+ 또한 사람의 이름이나 인용구 등을 포함하는 텍스트를 작성할 때도 고려할 필요가 있다.
  
이점  
아래와 같은 사람들이 콘텐츠를 더 잘 이해할 수 있다.
+ 단어를 해독하기 어려운 사람들
+ 맥락을 통해 이해하는 데 어려움이 있는 사람들
+ 단어를 소리내어 읽는 기술을 사용하는 사람들

적용방법  
일본어의 경우 아래와 같이 한자 다음 괄호로 그 한자의 발음을 추가로 제공하는 방법이 있다.
```html
<p> 慶應大学 (け い お う だ い が く) </ p>
```
발음에 따라 의미가 달라지는 등 단어의 발음이 중요한 영향을 끼친다면 해당 단어를 발음하는 사운드 파일이나, 발음 정보를 포함하는 사전의 항목 혹은 해당 발음의 IPA 표현, 해당 발음의 명확한 음성 철자, 해당 발음의 정보가 포함된 단어집에 연결할 수도 있다. 
  
사례
## 3.2 Predictable
웹 페이지가 예측 가능한 방식으로 나타나고 작동되도록 한다.

### 3.2.1 On Focus
>(Level A) 컴포넌트가 포커스를 받으면 컨텍스트를 변경하지 않는다.
  
목적  
+ 이는 웹 페이지를 탐색할 때 기능을 예측할 수 있도록 포커스를 받을 때 이벤트를 트리거 할 수 있는 구성 요소(사용자 인터페이스 요소)가 내용을 변경해서는 안됨을 의미한다.
+ 구성 요소가 포커스를 받을 때 자동으로 제출되는 양식이나,
+ 구성 요소가 포커스를 받을 때 실행되는 새 창, 혹은
+ 구성 요소가 포커스를 받을 때 포커스가 다른 구성 요소로 변경 등
+ 위와 같은 상황이 발생하면 안 된다.

  
이점
아래와 같은 사람들이 예상치 못한 상황에 처할 가능성을 줄일 수 있다.
+ 시각 장애, 인지 제한 혹은 운동 장애가 있는 사람들
  
적용방법  
새 창을 열기 위해 onfocus를 사용하는 대신 버튼을 클릭 또는 스페이스 바 사용을 할 때만 새 창을 팝업하는 방법이 있다.
  
또한 제출 버튼은 사용자가 완료 버튼을 탭했을 때 다음 화면이 자동으로 나타나는 대신 다음 데이터 입력 화면으로 이동하는 데 사용된다.
  
사례  
+ [대한항공 드롭메뉴](https://www.koreanair.com/kr/ko)를 보면 현재 운송 제한 물품에 포커스가 가 있지만 새 창이 열리거나 다른 구성 요소로 변경되고 있지 않다. 포커스가 가 있는 상태에서 클릭 혹은 스페이스 바, 엔터 키 등을 사용해야 다음 작업이 일어난다.
    ![3.2.1 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_2_1_ex01.png)


### 3.2.2 On Input
> (Level A) 사용자 인터페이스 컴포넌트의 설정을 변경해도 사용자가 해당 컴포넌트를 사용하기 전에 설정 변경에 관한 안내를 받지 않았다면 컨텍스트가 자동으로 변경되지 않는다.

목적  
+ 이는 데이터를 입력하거나 양식 컨트롤을 선택했을 때 예측가능한 효과가 있어야함을 의미한다.
+ 확인란을 선택하거나 텍스트 필드에 텍스트를 입력하거나 목록 컨트롤에서 선택한 옵션을 변경하면 설정이 변경되지만, 링크나 버튼을 활성화하면 변경되지 않는다.


이점  
아래와 같은 사람들이 예상치 못한 상황에 처할 가능성을 줄일 수 있다.
+ 새 창이 팝업되는 등 시각적 맥락이 언제 변경되었는지 알기 어려운 시각 장애가 있거나 시력이 약한 사람들
+ 시각 신호를 해석하는 데 어려움이 있어 문맥의 변화를 감지하기 위해 추가 단서가 필요한 시각 장애, 읽기 장애 및 지적 장애가 있는 사람들

적용방법  
문맥을 변경하는 각 양식 제출 버튼을 제공하는 방법이 있다. 제출 버튼의 용도는 양식에 입력된 데이터를 제출하는 HTTP 요청을 생성하는 것이므로 문맥 변경을 발생시킬 때 사용하기에 적절하고 예측할 수 있게 해준다.
```html
<form action="http://www.example.com/cgi/subscribe/" method="post"><br /> 
 <p>Enter your e-mail address to subscribe to our mailing list.</p><br /> 
 <label for="address">Enter email address:</label><input type="text" 
 id="address" name="address" /> 
 <input type="submit" value="Subscribe" /><br /> 
</form>
```  

&lt;input&gt; 요소가 image 타입인 경우에 한하여, alt 속성을 submit으로 주어 해당 이미지는 버튼의 의미를 가짐을 알려줄 수도 있다. 그러면 사용자가 이 이미지를 클릭 혹은 스페이스바를 눌렀을 때, 어떤 문맥의 변화가 일어날 것이라 예측할 수 있다.
```html
<form action="http://example.com/prog/text-read" method="post">
  <input type="image" name="submit" src="button.gif" alt="Submit" />
</form>    
```

양식 컨트롤의 변경으로 문맥이 변경될 때 발생하는 상황에 대한 정보를 텍스트 지침 혹은 aria-label 속성을 이용해 미리 제공할 수도 있다. 
+ 설정 변경에 의해 문맥이 변경되는 사용자 인터페이스 요소보다 앞선 읽기 순서로 웹 페이지에서 지침을 제공하거나, 
+ 사용자 인터페이스 요소에 도달하기 위해 특정 단계를 완료해야하는 다단계 프로세스의 경우 변경사항이 발생하기 전에 프로세스의 일부를 지침으로 제공할 수 있다. 혹은, 
+ 웹 애플리케이션을 사용하기 전에 사용자 교육이 필요한 인트라넷의 경우 설정 변경 시 컨텍스트 변경을 유발하는 사용자 인터페이스 요소가 교육의 일부로 제공될 수 있다.

사례  
+ [네이버 로그인 폼](https://nid.naver.com/nidlogin.login?mode=form&url=https%3A%2F%2Fwww.naver.com)을 보면 로그인 버튼이 submit으로 제출 버튼으로 제공되어 문맥 변화를 예측할 수 있다.
    ![3.2.2 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_2_2_ex01.png)

+ [이케아 언어변경 탭](https://www.ikea.com/kr/ko/)을 보면 언어 변경을 선택하여 문맥에 변경이 생기기 전에, aria-label 속성을 이용해 원하시는 언어를 선택하세요라는 정보를 주어 언어를 변경하면 변경 사항이 생길 것임을 예측할 수 있게 한다.
    ![3.2.2 example 02](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_2_2_ex02.png)


### 3.2.3 Consistent Navigation
> (Level AA) 일련의 웹 페이지 내에서 여러 웹 페이지에 반복되는 탐색 메커니즘은 사용자가 변경을 개시하지 않는 한 반복될 때마다 동일한 상대 순서로 발생한다.

목적
+ 웹 페이지 내에서 반복되는 콘텐츠와 상호작용하고 특정 정보나 기능을 두 번 이상 찾아야하는 사용자에게 일관된 화면 및 레이아웃을 제공해야함을 의미한다. 
+ 즉, 사용자가 반복해서 탐색하며 원하는 콘텐츠를 찾을 때, 해당 콘텐츠의 위치를 예측할 수 있어야한다는 것이다.
+ 반복되는 구성 요소가 사이트의 각 페이지에서 동일한 순서로 발생하도록 하여 사용자가 각 페이지에서 항목을 찾을 수 있는 위치를 예측할 수 있다는 확신을 가질 수 있게 한다.

이점  
아래와 같은 사람들이 좀 더 쉽게 원하는 콘텐츠를 찾을 수 있다.
+ 인지적 한계 혹은 저시력, 지적 장애, 시력 상실 등을 가진 사람들 

적용방법
검색 필드를 사이트의 모든 웹 페이지의 맨 마지막 항목으로 두어 사용자가 검색 기능을 빠르게 찾을 수 있도록 하는 것과 같이 일관 되게 컨트롤 버튼을 위치시키는 방법이 있다.
  
네비게이션 건너 뛰기 혹은 주요 컨텐츠로 건너 뛰기 등의 링크를 모든 웹 페이지의 맨 첫번째 링크로 포함하여 이 링크를 통해 제목 정보 및 콘텐츠를 우회하고 싶을 때 바로 찾을 수 있도록 건너 뛰기 탐색 컨트롤 역시 일관되게 배치할 수 있다.

확장 탐색 메뉴를 제공하여 사용자가 하위 탐색 항목을 상위 탐색 메뉴에 삽입하여 예측가능한 메뉴를 만들 수 있게 한다.  


사례  
+ [대한항공 상단 탭](https://www.koreanair.com/kr/ko)의 경우 어떤 페이지를 들어가도 항상 같은 위치, 같은 순서로 제공되어 사용자가 각 메뉴의 위치를 예측할 수 있다.
    ![3.2.3 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_2_3_ex01.png)



### 3.2.4 Consistent Identification
> (Level AA) 웹 페이지 내에서 기능이 동일한 컴포넌트는 일관되게 식별된다.

목적  
+ 웹 페이지 내에서 반복적으로 나타나는 기능 구성 요소를 일관되게 식별할 수 있어야함을 의미한다.
+ 동일한 기능에 대해 다양한 레이블이나 텍스트 대체 요소가 있으면 이를 식별하기 어렵다.

이점  
아래의 사람들이 예측가능한 작업을 할 수 있다.
+ 대체 텍스트에 의존하는 사람들
+ 텍스트를 읽거나 대체 텍스트를 감지하는데 어려움이 있는 사람들

적용방법
동일한 기능을 가진 아이콘은 모든 웹 페이지에서 동일한 아이콘을 사용하고, 아이콘의 대체 텍스트도 동일하게 사용하는 방법이 있다.
  
온라인 기사를 게시하는 웹 사이트의 경우 각 기사에 기사의 첫 페이지, 다음 페이지 및 이전 페이지에 대한 링크가 있을 때 각 링크를 페이지1, 페이지2, 페이지3와 같이 완전히 동일하지 않아도 일관성을 가지게 할 수도 있다.
  
사례
+ []()

### 3.2.5 Change on Request
> (Level AAA) 컨텍스트의 변경이 사용자 요청에 의해서만 일어나거나 그러한 변화를 중지할 수 있는 메커니즘을 이용할 수 있다.

목적
+ 이는 사용자에게 문맥 변경을 완전히 제어할 수 있게 해야함을 의미한다.
+ 새 창 자동실행, 목록에서 항목 선택 후 양식 자동 제출 등과 같이 예상할 수 없는 문맥 변경으로 인한 혼란이 없어야 한다.


이점  
아래의 사람들이 예상치 못한 상황에 마주하는 것을 방지한다.
+ 운동장애가 있는 사람들
+ 새 창이 팝업되는 것과 같은 시각적 상황 변화를 인지하기 어려운 저시력자 및 시각 장애인
+ 시각 신호를 해석하는 데 어려움이 있는 저시력자, 인지 제한이 있는 사람들

적용방법
콘텐츠를 업데이트 해야할 때, 자동으로 진행하는 것이 아닌 &lt;a&gt; 태그나 &lt;link&gt; 등을 사용하여 콘텐츠 새로 고침을 요청하는 업데이트 단추를 제공하는 등 사용자가 변화를 제어할 수 있도록 하는 방법이 있다.
```html
<a href="news.jsp">Update this page</a>
```

target 속성을 사용하여 자동 팝업 대신 새 창으로 열릴 것이라고 분명하게 기계가 판독할 수 있도록 제공한다.
```html
<a href="help.html" target="_blank">Show Help (opens new window)</a>
```

사례
+ [하나은행 로그인 페이지](https://www.kebhana.com/common/login.do)에서 로그인을 하려고 할 때, 보안 프로그램이 설치가 필요한 경우 설치화면으로 이동한다는 메세지를 주고, 확인 버튼을 눌러야 이동하게끔 되어있다.
  ![3.2.5 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_2_5_ex01.png)

## 3.3 Input Assistance
사용자가 실수를 피하고 바로잡을 수 있게 돕는다.

### 3.3.1 Error Identification
> (Level A) 입력 오류가 자동으로 감지되면 오류가 있는 항목을 식별하고 사용자에게 오류를 텍스트로 설명한다.

목적  
+ 이는 사용자가 오류가 발생했음을 인식하고 무엇이 잘못되었는 지 확인할 수 있도록 해야함을 의미한다.
+ 이때 오류 메세지는 가능한 구체적이어야 한다.

이점  
+ 시각 장애가 있거나 색맹이 있어 텍스트로 된 오류 메세지가 필요한 사용자들
+ 아이콘과 기타 시각적 단서가 나타내는 의미를 이해하는 데 어려움이 있는 인지, 언어 및 학습 장애가 있는 사람들

적용방법  
필수로 작성하거나 선택해야하는 필드에 aria-invalid 속성 및 aria-describedby 속성을 이용할 수도 있다. 그러면 필드 누락으로 양식 제출이 실패했음을 메세지로 알려준다.
```html
<code>
<script>
...
...
		if ($('#first').val() === '') {
			$('#first').attr("aria-invalid", "true");
$("label[for='first']").addClass('failed');
		}
		if ($('#last').val() === '') {
			$('#last').attr("aria-invalid", "true");
$("label[for='last']").addClass('failed');
		} 
		if ($('#email').val() === '') {
			$('#email').attr("aria-invalid", "true");
$("label[for='email']").addClass('failed');
		} 
...
...
</script>
<style type="text/css">
label.failed {
	border: red thin solid;
}
</style>
<form name="signup" id="signup" method="post" action="#">
 <p>
    <label for="first">First Name (required)</label><br>
    <input type="text" name="first" id="first">
  </p>
  <p>
    <label for="last">Last Name (required)</label><br>
    <input type="text" name="last" id="last">
  </p>
  <p>
    <label for="email">Email (required)</label><br>
    <input type="text" name="email" id="email">
  </p>
  <p>
    <input type="submit" name="button" id="button" value="Submit">
  </p>
</form>
</code> 
```

양식에 유효한 데이터가 입력되었는지 자바스크립트 함수로 확인하고 alert()함수로 오류 메세지를 출력하도록 이벤트 핸들러를 이용할 수도 있다.
```html
<label for="date">Date:</label>
<input type="text" name="date" id="date" 
onchange="if(isNaN(Date.parse(this.value))) 
alert('This control is not a valid date. 
Please re-enter the value.');" />
```

사용자가 제공하는 정보가 특정 데이터 형식 또는 특정 값이어야하는 경우에는 aria-alertdialog 속성 혹은 aria role = alert 속성 등을 사용하여 오류를 식별할 수도 있다.
```html
<div role="alertdialog" aria-labelledby="alertHeading" aria-describedby="alertText">
<h1 id="alertHeading">Error</h1>
<div id="alertText">Employee's Birth Date is after their hire date. Please verify the birth date and hire date.</div>
<button>Save and Continue</button>
<button>Return to page and correct error</button>
</div>
```

사례
+ [네이버 회원가입 페이지](https://nid.naver.com/user2/V2Join?token_sjoin=65g3bc0DoiWreVk0&langSelect=ko_KR&chk_all=on&termsService=on&termsPrivacy=on&termsLocation=Y&termsEmail=Y)에서 비밀번호 입력과 비밀번호 확인 입력 요소에 aria-describedby 속성을 이용하여 필드 누락으로 양식 제출이 실패했음을 메세지로 알려주고 있다.
  ![3.3.1 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_3_1_ex01.png)


### 3.3.2 Labels or Instructions
> (Level A) 사용자 입력이 필요한 콘텐츠에는 레이블이나 지침이 제공된다.

목적  
+ 이는 양식을 완료하는 데 도움이 되도록 지침을 제공되어야 함을 의미한다.
+ 특히 관습적인 형식을 벗어나거나 올바른 입력을 위한 특정 규칙이 있는 경우, 지침 또는 레이블에서 데이터 형식을 지정할 수도 있다.
+ 지침이 길고 장황한 경우, 개별 컨트롤에 초점이 있는 경우에만 지침을 사용하도록 선택하게 할 수도 있다.
+ 너무 많은 정보는 오히려 혼동을 줄 수 있으므로 작업을 수행하기위해 필요한 수준에서 충분한 정보를 제공해야 한다.

이점  
+ 인지, 언어 및 학습 장애가 있는 사용자를 포함하여 모든 사용자가 정보를 올바르게 입력하는 데 도움이 된다.
+ 명확하고 모호하지 않은 레이블 및 지침을 제공하면, 사용자가 불완전하거나 잘못된 양식을 제출하는 것을 방지하여 제출 오류를 수정하기 위해 페이지 양식을 한번 더 탐색하지 않아도 된다.
  
적용방법  
aria-describedby 속성을 이용하여 버튼에 대한 자세한 정보를 제공하거나 지침을 양식 필드와 연결하는 방법이 있다.
```html
<button aria-label="Close" aria-describedby="descriptionClose"
    onclick="myDialog.close()">X</button>
...
<div id="descriptionClose">Closing this window will discard any information entered and
return you back to the main page</div>
```

aria-labelledby 속성을 사용하여 의미 있는 레이블이 둘 이상의 레이블 문자열로 구성되어야하는 상황에서 텍스트 입력 요소를 연결할 수도 있다.
```html
<form>
<p><span id="timeout-label" tabindex="-1"><label for="timeout-duration">Extend time-out to</label></span>
<input type="text" size="3" id="timeout-duration" value="20" 
    aria-labelledby="timeout-label timeout-duration timeout-unit">
<span id="timeout-unit" tabindex="-1"> minutes</span></p>
</form>
``` 
  
aria-labelledby 속성뿐 아니라 role 속성을 통해 양식 내 관련 컨트롤 집합을 그룹으로 표시할 수 있다. 사용자 인터페이스 디자인을 인해 fieldset-legend 기술을 사용하기 어려울 때 양식 컨트롤을 프로그래밍 방식으로 그룹화하는 대안이다.
```html
<div role="group" aria-labelledby="ssn1">
   <span id="ssn1">Social Security#</span> 
   <span style="color: #D90D0D;"> * </span>
   <input size="3" type="text" aria-required="true" title="First 3 digits" />-
   <input size="2" type="text" aria-required="true" title="Next 2 digits" />-
   <input size="4" type="text" aria-required="true" title="Last 4 digits" />
</div>
```
사례
+ [레진코믹스](https://www.lezhin.com/ko)의 경우 작품 검색 항목에서 aria-labelledby 속성을 이용하여 텍스트 입력 요소를 연결하고 있다.
  ![3.3.2 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_3_2_ex01.png)

### 3.3.3 Error Suggestion
> (Level AA) 입력 오류가 자동으로 감지되고 이를 정정하기 위한 추천 항목이 있다면 그 추천 항목이 콘텐츠의 보안이나 목적을 위태롭게 하지 않는 한 이를 사용자에게 제공한다.

목적
+ 이는 입력 오류가 있을 시, 해당 오류를 수정하기 위한 적절한 제안을 받도록 해야함을 의미한다.
+ 오류 알림을 제공하더라도 인지 한계가 있는 사람들은 오류를 수정하는 방법을 이해하기 어려울 수 있고, 시각 장애인의 경우 오류를 수정하는 방법을 정확히 파악하지 못할 수 있기 때문에 오류에 대한 설명을 제공해야 한다.
  
이점
+ 학습 장애가 있는 사람들, 시각장애가 있는 사람들이 입력 오류의 특성과 수정 방법을 더 쉽게 이해할 수 있다.
+ 동적 장애가 있는 사람들은 입력 값을 변경하는 데 필요한 횟수를 줄일 수 있다.
  
적용방법  
필수 양식 필드에 입력이 없다면 어디가 비었는지 알 수 있도록 텍스트로 정보를 제공하는 방법이 있다. title화면 판독기 사용자는 페이지가 올바르게 제출되었다고 생각하고 새 페이지가 반환되는 즉시 다른 페이지로 계속 이동하기 때문에 페이지 제목에 오류 알림을 포함하는 것이 좋다.

필수 양식 필드에 aria-required 속성을 ture로 주어 해당 부분을 작성하지 않았을 시, 필수 항목이 빠졌다는 오류 메세지를 발생시킬 수도 있다.
```html
<form action="#" method="post" id="step1" onsubmit="return errorCheck2()">
  <p>
    <label for="fname">First name: </label>
    <input type="text" id="fname" aria-required="true" />
    [required]
  </p>
  <p>
    <label for="mname">Middle name: </label>
    <input type="text" id="mname" />
  </p>
  <p>
    <label for="lname">Last name: </label>
    <input type="text" id="lname" aria-required="true" />
    [required]
  </p>
  <p>
    <label for="email">Email address: </label>
    <input type="text" id="email" aria-required="true" />
    [required]
  </p>
  <p>
    <label for="zip_post">Zip / Postal code: </label>
    <input type="text" id="zip_post" size="6" aria-required="true" />
    [required]
  </p>
  <p>
    <input type="submit" value="Next Step" id="step_btn" name="step_btn" />
  </p>
</form> 
```
  
aria-alertdialog 속성을 사용하여 잘못된 정보를 입력한 사람에게 알림으로 알려줄 수도 있다.
```html
<div role="alertdialog" aria-labelledby="alertHeading" aria-describedby="alertText">
<h1 id="alertHeading">Error</h1>
<div id="alertText">Employee's Birth Date is after their hire date. Please verify the birth date and hire date.</div>
<button>Save and Continue</button>
<button>Return to page and correct error</button>
</div>
```
  
입력의 형식, 값 및 유형에 대한 제한이 있을 때, 사용자가 제공한 정보가 허용되지 않고 가능한 올바른 텍스트가 있는 경우, 올바른 텍스트를 제공할 수도 있다.

사례
+ [레진코믹스](https://www.lezhin.com/ko)의 경우 레진 패스 결제 시, role="alertdialog"를 통해 해당 결제 항목에 대한 정보를 제공한다. 
  ![3.3.3 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_3_3_ex01.png)
  
### 3.3.4 Error Prevention(Legal, Financial, Data)
> (Level AA) 사용자에 대한 법적 책임이나 금융 거래가 발생하는 웹 사이트가 데이터 스토리지 시스템에서 사용자가 제어할 수 있는 데이터를 수정 또는 삭제하거나 사용자 테스트 응답을 제출하는 경우, 다음 중 하나 이상을 만족한다.
> + 복원 가능(Reversible): 제출 내용을 복원할 수 있다.
> + 점검(Checked): 사용자가 입력한 데이터에 입력 오류가 있는 지 점검하고 오류를 수정할 수 있는 기회를 사용자에게 제공한다.
> + 확인(Confirmed): 제출을 완료하기 전엔 정보를 검토, 확인, 수정하는 메커니즘을 이용할 수 있다.

목적  
+ 이는 장애가 있는 사람들이 환불 불가 항공권구매, 중개 계좌에서 주식 구매 등 되돌릴 수 없는 작업을 수행할 때, 실수로 인한 심각한 결과를 피할 수 있도록 하기 위함이다.

이점
+ 실수할 가능성이 더 큰 모든 장애가 있는 사람들이 실수로 인한 심각한 결과를 방지하기 위해 보호 장치를 제공할 수 있다.
   
적용방법
온라인 쇼핑 시, 주문이 제출되면 사용자가 주문의 정확성을 검사할 수 있도록 주문 항목, 각 주문 항목의 수량, 배송지 주소 및 결제 방법등을 포함한 주문정보를 표시하여 사용자가 주문을 확인하거나 변경할 수 있도록 하는 것처럼 정보를 제공하는 방법이 있다.
온라인 뱅킹에서 입금처 및 입금 금액 등 거래에 대한 요약이 제공되는 것도 같은 이치이다.
  
결제 및 거래 전 체크 박스를 선택하도록 하여 해당 체크 박스를 선택했을 시 결제 및 거래가 진행되도록 할 수도 있다. 이때, 이 체크 박스를 선택하면 어떤 일이 발생하는 지에 대한 설명이 필요하다.

사례
+ [알라딘](https://www.aladin.co.kr/home/welcome.aspx)을 비롯한 많은 쇼핑몰에서 결제 후 결제에 대한 정보를 보여 주어 입력한 정보를 조회, 변경, 취소 가능하도록 기능을 제공하고 있다.
  ![3.3.4 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_3_4_ex01.png)


### 3.3.5 Help
> (Level AAA) 상황에 맞는 도움말(context-sensitive help)을 이용할 수 있다.

목적  
+ 이는 사용자가 실수를 하지 않도록 돕기 위한 것이다. 
+ 일부 장애가 있는 사람들은 장애가 없는 사람들보다 실수를 할 가능성이 더 높기 떄문에 상황에 맞는 도움말을 사용하여 수행중인 작업을 추적하지 않고 작업을 수행하는 방법을 알려줘야 한다.
+ 레이블이 모든 기능을 설명하기에 충분하지 않은 경우에만 제공하면 되며 필요할 때마다 분명하게 얻을 수 있어야 한다.
  
이점  
아래와 같은 사람들을 돕는다.
+ 텍스트 입력이 필요한 양식에 텍스트를 작성하는데 종종 어려움을 겪는 읽기 및 지적 장애가 있는 사람들
+ 쓰기 장애가 있는 사람들
+ 노화로 인해 텍스트 입력 및 마우스 조작에 동일한 어려움이 있는 사람들
   
적용방법  
온라인 입사 지원의 경우, 일부 질문은 새로운 구직자가 이해하기 어려울 수 있다. 이때 각 질문 옆에 있는 도움말 링크가 각 질문에 대한 지침과 설명을 제공하는 방법이 있다. 아래와 같이 도움말 링크를 통해 스크린 리더 사용자가 입력 양식 컨트롤과 상호작용할 때, 해당 링크에 접근할 수 있도록 한다.
```html
<form action="test.html">
  <label for="test">Test control
  <a href="help.html" target="_blank">Help</a></label>
  <input type="text" name="test" id="test" />
</form>
```
  
양식 제출이 필요할 때, 양식 상단에 "날짜는 mm/dd/yyyy 형식으로 입력해야합니다." 등의 텍스트 메세지를 미리 제공하여 설명할 수도 있다.
  
사례  
+ [구글 회원가입 페이지](https://accounts.google.com/signup/v2/webcreateaccount?continue=https%3A%2F%2Fwww.google.com%2F%3Fhl%3Dko&hl=ko&gmb=exp&biz=false&flowName=GlifWebSignIn&flowEntry=SignUp)를 보면, 이 이메일이 본인 소유인지 확인해야합니다. 라는 메세지나 문자,숫자,기호를 조합하여 8자 이상을 사용하세요. 등 입력 요소의 양식을 텍스트 메세지를 통해 제공하고 있다.
  ![3.3.5 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Understandable/assets/3_3_5_ex01.png)

### 3.3.6 Error Prevention(All)
> (Level AAA) 사용자가 정보를 제출해야 하는 웹 페이지의 경우 다음 중 하나 이상을 만족한다.
> + 복원 가능(Reversible)L 제출 내역을 복원할 수 있다.
> + 점검(Checked): 사용자가 입력한 데이터에 입력 오류가 있는 지 점검하고 오류를 수정할 수 있는 기회를 사용자에게 제공한다.
> + 확인(Confirmed): 제출을 완료하기 전에 정보를 검토, 확인, 수정하는 메커니즘을 이용할 수 있다.

목적  
+ 이는 장애가 있는 사람들이 양식 데이터를 제출할 때, 실수로 인해 발생할 수 있는 결과를 피할 수 있도록 돕기 위함이다. 
+ 이 기준은 위의 3.3.4를 기반으로 한다.
+ 장애가 있는 사람들은 실수할 가능성이 더 높고, 실수를 감지하거나 복구하기에 어려울 수 있다.
+ 이때 복원 기능, 점검 기능, 확인 기능을 제공하면 사용자가 실수를 감지할 수 있다.

이점  
+ 실수로 인한 결과를 방지하기 위한 보호 장치로, 실수할 가능성이 큰 모든 장애가 있는 사람들에게 도움이 된다.

적용방법  
3.3.4를 기반으로 하여, 3.3.4를 참고.
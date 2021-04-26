# 4. Robust
콘텐츠는 보조 기술 등의 다양한 사용자 에이전트를 이용해 확실히 해석할 수 있을 정도로 충분히 견고해야 한다.

## 4.1 Compatible
보조 기술을 포함해, 현재와 미래의 사용자 에이전트와의 호환성을 극대화한다.

### 4.1.1 Parsing
> (Level A) 마크업 언어를 이용해 구현한  콘텐츠에서 요소에는 완전한 시작/종료 태그가 있고, 요소의 중첩 구조는 표준에 따라 만들어지며, 요소에 중복된 속성은 포함되지 않는다. 또한 표준에서 허용한 경우를 제외하고, 모든 ID의 값은 고유하다.
> 가령 닫는 괄호처럼 태그 형성에 필수적인 문자가 빠진 시작/종료 태그나 일치하지 않는 속성 값 물음표는 완전하지 않다.

목적  
+ 이는 보조 기술을 포함한 사용자 에이전트가 콘텐츠를 정확하게 해석하고 구문 분석할 수 있도록 해야함을 의미한다. 
+ 콘텐츠를 데이터 구조로 구문 분석을 할 수 없는 경우, 다른 사용자 에이전트는 콘텐츠를 다르게 표시하거나 완전히 구문 분석을 할 수 없기 때문이다.

이점
+ 웹 페이지에 완전한 시작 및 끝 태그가 있고 사양에 따라 중첩되도록 하면, 보조 기술일 충돌없이 콘텐츠를 정확하게 구문 분석할 수 있다.
  
적용방법  
개발자가 오프라인 또는 온라인 유효성 검사기를 이용하여 HTML, XML 유효성 검사를 진행하는 방법이 있다. 해당 검사기에서 오류가 검출되지 않도록 잘 구성해야 한다.

또한, HTML 및 XHTML 사용 시, 사양에 정의된 기능만 사용해야하며, 사양에 규정된 방식으로 기능을 사용해야한다.

사례
+ [chorome web developer](https://chrispederick.com/work/web-developer/)를 사용하여 HTML 및 XML, CSS의 유효성 검사를 진행할 수 있다.
    ![4.1.1 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Robust/assets/4_1_1_ex01.PNG)


### 4.1.2 Name, Role, Value
>(Level A) 모든 사용자 인터페이스 컴포넌트(다음 항목을 포함하되 여기에 국한되지 않음: 스크립트로 생성한 폼 요소, 링크, 컴포넌트)에 대해, 이름(name)과 역할(role)을 프로그래밍 방식을 확인할 수 있고, 사용자가 설정할 수 있는 상태(status)와 프로퍼티(properties), 값(values)을 프로그래밍 방식으로 설정할 수 있으며, 이러한 항목들이 변경되었을 때는 보조 기술을 포함한 사용자 에이전트에 알림이 제공된다.

목적  
+ 이는 보조 기기가 콘텐츠의 사용자 인터페이스 컨트롤 상태에 대한 정보를 수집하고 활성화하고 최신상태로 유지할 수 있도록 해야함을 말한다.

이점  
+ 모든 사용자 인터페이스 구성 요소에 대한 역할, 상태 및 가치 정보를 제공하면 장애가 있는 모든 사용자가 사용하는 스크린 리더, 화면 돋보기 및 음성 인식 소프트웨어와 같은 보조 기술과의 호환성이 가능하다

적용방법  
aria-label 속성을 사용하여 버튼에 엑세스 가능한 이름을 제공하는 방법이 있다.
```html
<div id="box">
   This is a pop-up box.
   <button aria-label="Close" onclick="document.getElementById('box').style.display='none';" class="close-button">X</button>				
</div>
```

role 속성을 사용하여 해당 구조를 명확하게 전달할 수 있다.
```html
<ul role="tree" tabindex="0">
  <li role="treeitem">Birds</li>
  <li role="treeitem">Cats
    <ul role="group">
      <li role="treeitem">Siamese</li>
      <li role="treeitem">Tabby</li>
    </ul>
  </li>
  <li role="treeitem">Dogs
    <ul role="group">
      <li role="treeitem">Small Breeds
        <ul role="group">
          <li role="treeitem">Chihuahua</li>
          <li role="treeitem">Italian Greyhound</li>
          <li role="treeitem">Japanese Chin</li>
        </ul>
      </li>
      <li role="treeitem">Medium Breeds
        <ul role="group">
          <li role="treeitem">Beagle</li>
          <li role="treeitem">Cocker Spaniel</li>
          <li role="treeitem">Pit Bull</li>
        </ul>
      </li>
      <li role="treeitem">Large Breeds
        <ul role="group">
          <li role="treeitem">Afghan</li>
          <li role="treeitem">Great Dane</li>
          <li role="treeitem">Mastiff</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>
```
  
iframe 요소 사용시, title 요소를 추가하여 해당 iframe이 어떤 용도인지 확실하게 알려줄 수도 있다.
```html
<iframe src="banner-ad.html" id="testiframe" 
  name="testiframe" title="Advertisement">
    <a href="banner-ad.html">Advertisement</a>
</iframe>
```
사례
+ [네이버 메인 화면](www.naver.com)을 보면 banner인 부분은 role = banner 로, main인 부분은 role = main으로 구성 요소에 대한 역할을 확실하게 한 것을 볼 수 있다. 또한 iframe 요소의 경우 title로 쇼핑캐스트를 주어 해당 iframe이 어떤 용도인지 확실하게 알려준다. 
    ![4.1.2 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Robust/assets/4_1_2_ex01.PNG)

### 4.1.3 Status Messages
> (Level AA) 마크업 언어로 구현된 컨텐츠에서 상태 메시지는 역할이나 속성을 통해 프로그래밍 방식으로 확인할 수 있으므로 포커스를 받지 않고 보조 기술로 사용자에게 제공할 수 있다.

목적  
+ 이는 사용자가 초점이 맞지 않는 콘텐츠의 중요한 변경 사항을 사용자에게 알리고 불필요하게 작업을 중단하지 않는 방식으로 수행할 수 있도록 하는 것이다.

이점
+ 상태 메세지에 적절한 역할 또는 속성이 할당되면, 스크린 리더 기능이 있는 보조 기술의 시각 장애인 및 저시력 사용자들에게 추가 정보를 제공할 수 있다.
  
적용방법  
role 속성에 alert를 주어 컨터이너에 오류 메세지를 삽입하는 방법이 있다. 이는 aria-live에 assertive를 사용하는 것과 동일한 결과를 낼 수 있다.


사례
+ [네이버 로그인 페이지](https://nid.naver.com/nidlogin.login)에서 로그인이 실패했을 때  나오는 가입하지 않은 아이디이거나, 잘못된 비밀번호 입니다. 메세지는 aria-live = "assertive" 속성을 가지고 삽입되어 해당 메세지에 포커스가 가지 않은 상태로 해당 메세지를 전달하고 있다.
  ![4.1.3 example 01](https://github.com/HyunJungC-Dev/WCAG/blob/main/04_team/Robust/assets/4_1_3_ex01.PNG)

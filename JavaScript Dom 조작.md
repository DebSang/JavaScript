## JavaScript Dom 조작

> DOM 조작

- Document는 문서 한 장(HTML)에 해당하고, 이를 조작
- 조작 순서
  1. 선택(Seletc)
  2. 변경(Manipulation)



> DOM 관련 객체의 상속 구조

- EventTarget
  - Event Listener를 가질 수 있는 객체가 구현하는 DOM인터페이스
- Node
  - 여러 가지 DOM 타입들이 상속하는 인터페이스
- Element
  - Document 안의 모든 객체가 상속하는 가장 범용적인 인터페이스
- Document
  - 브라우저가 불러온 웹 페이지
  - DOM 트리의 진입점 역할을 수행
- HTMLElement
  - 모든 종류의 HTML요소
  - 부모 element의 속성 상속



> DOM 선택 관련 메서드

- document.**querySeletor**(selector)
  - 제공한 `선택자`와 일치하는 element 하나 선택
  - 제공한 CSS selector를 만족하는 <u>첫 번째 element 객체를 반환, 없으면 null</u>
- document.**querySeletorAll**(selector)
  - 제공한 `선택자`와 일치하는 모든 element 선택
  - 매칭 할 하나 이상의 셀렉터를 포함하는 유효한 CSS selector를 인자(문자열)로 받음
  - 지정된 셀렉터에 일치하는 <u>NodeList를 반환</u>



> DOM 선택 -HTMLCollection & NodeList

- 둘 다 배열처럼 각 항목에 접근하기 위한 index 제공
- HTMLCollection
  - name, id, index 속성으로 각 항목 접근
- NodeList
  - index로만 각 항목에 접근 가능
  - 단, HTMLCollection과 달리 배열에서 사용하는 forEach 메서드 및 다양한 메서드 사용 가능
- 둘다 Live Colletcion으로 DOM의 변경사항을 실시간으로 반영하지만, <u>querySeletorAll()에 의해 반환되는 NodeList는 실시간 반영 X</u>



> DOM변경 관련 메서드

- document.**createElement**()
  - 작성한 태그 명의 HTML 요소를 생성하여 반환
- Element.**append**()
  - 특정 부모 Node의 자식 NodeList 중 마지막 자식 다음에 Node 객체나 DOMString을 삽입
  - 여러 개의 Node 객체, DOMString을 추가할 수 잇음
  - 반환 값이 없음
- Node.**appendChild**()
  - 한 Node를 특정 부모 Node의 자식 NodeList 중 마지막 자식으로 삽입(Node만 추가 가능)
  - 한번에 오직 하나의 Node만 추가
  - <u>만약 주어진 Node가 이미 문서에 존재한 다른 Node를 참조한다면 새로운 위치로 이동</u>



> DOM 변경 관련 속성

- Node.**innerText**
  - Node 객체와 그 자손의 텍스트 컨텐츠(DOMString)를 표현 
  - 줄 바꿈을 인식하고 숨겨진 내용을 무시하는 등 최종적으로 스타일링이 적용된, 사람이 읽을 수 있는 요소만 남김
- Element.**innerHTML**
  - 요소(element) 내에 포함된 HTML 마크업을 반환
  - XSS공격에 취약



> DOM 삭제 관련 메서드

- ChildNode.**remove**()
  - Node가 속한 트리에서 해당 Node를 제거
- Node.**removeChild**()
  - DOM에서 자식 Node를 제거하고 제거된 Node를 반환
  - Node는 인자로 들어가는 자식 Node의 부모 Node



> DOM 속성 관련 메서드

- Element.**setAttribute(name, value)**
  - 지정된 요소의 값을 설정
  - 속성이 이미 존재하면 값을 갱신, 없으면 새 속성 추가
- Element.**getAttribute(attributeName)**
  - 해당 요소의 지정된 값을 반환
  - 인자는 값을 얻고자 하는 속성의 이름
### JQuery

##### JQuery 요소 선택

* $(선택자) : 달러표시는 제이쿼리를 의미
  
  * 태그명, 클래스명, 아이디 등 모든 선택자 사용 가능
  
  * JQuery를 이용해 요소를 선택해오면 반환값은 JQuery 배열

* css 속성 변경방법
  
  * css(속성명, 값);
  
  * $("선택자").css("속성명", "값");
  
  * 대상요소.css("속성명", "값");

* JQuery 의 이벤트
  
  * $("선택자").on("이벤트명", 콜백함수)

* JQuery를 이용하면 하나의 요소나 여러개의 요소에 같은 방식으로 이벤트 리스너 추가가 가능하여 간편
  
  * 대상요소.append(값/요소) : 대상요소를 기준으로 그 요소의 안쪽에(자식)값이나 요소를 뒤로 추가하고 싶을때 사용하는게 append
  
  * 대상요소append(값/요소) : 대상요소 기준 그 요소의 안쪽(자식)값이나 요소를 뒤로 추가하고 싶을때 사용
  
  * 대상요소.prepend(값/요소) : 대상요소 안쪽의 기존 요소를 기준으로 앞쪽에 추가
  
  * ex) div태그면서 클래스명에 div가 포함되는 div에 마우스가 올라가면 진입이라는 문자열을 원래 문자열뒤에 추가
  
  * $("div[class*=Div]").on("mouseover", function(){
    
    $(this).append("진입"); })

* 동적요소
  
  * 페이지가 로드되었을 때에 존재하지 않았던, 사용자의 액션이나 혹은 서버와의 통신에 따른 결과값으로 페이지에 추가되는 요소들을 동적 요소라고 표현함

* 동적 요소 추가
  
  * window onload : 브라우저 안쪽의 모든 요소가 다 준비가 완료됐을때
  
  * document ready : document 객체와 관련된 요소들이 다 생성이 됐을때
  
  * 대상요소.append() : 대상요소의 안쪽에 기존요소 뒤쪽으로 요소/값 추가
  
  * JQuery를 이용하면 텍스트로 만들어준 요소도 요소 자체로 추가 가능
  
  * ex) 1. let newElement = "추가하고 싶은 요소"
    
          $("선택자").append(newElement);
  
  * ex) 2. $(newElement).appendTo(선택자);
  
  * 대상요소.prepend(추가할 요소) : 대상 요소를 기준으로 안쪽에 최상단에 요소를 추가
  
  * before() : 동위관계에 있어 요소의 앞쪽에다가 요소를 추가
  
  * after() : 동위관계에 있어 요소의 뒤쪽에다가 요소를 추가

* 부모_자식 관계
  
  * 자식 선택 대상요소.children() : 대상요소 기준으로 바로 아래 자식만 모두 선택
  
  * 선택자의 자식선택하여 css 속성주기
  
  * ex) 자식 선택 대상요소.children().css({"border":2px dotted grey, "width" : "300px"})
  
  * 대상요소의 바로 아래 자식 중에서 선택자에 해당하는 자식(첫번째 태그가 p태그인 자식만 선택)만 선택하여 css 속성주기
  
  * ex) 대상요소.children("태그:first-child").css({"border":2px dotted grey, "width" : "300px"})
  
  * 대상요소.find(선택자) : 대상요소를 기준으로 하위 요소 중 모든 선택자에 해당하는 요소를 모두 선택하여 css 속성주기
  
  * ex) 대상요소.find("태그").css({"background-color" : "pink"})
  
  * eq(요소의 인덱스 번호) : 인덱스번호에 해당하는 요소 선택
  
  * ex) 대상요소.find("태그").eq(인덱스번호).css(속성);
  
  * 대상요소.parent() : 대상요소를 기준으로 부모 요소를 선택
  
  * 대상요소.parents() : 대상요소를 기준으로 모든 상위 요소를 선택

* 형제 선택
  
  * 대상요소.next() : 대상요소를 기준으로 다음에 오는 요소 선택
  
  * ex) $(대상요소).next().속성
  
  * 대상요소.siblings(): 대상요소를 기준으로 모든 형제 요소 선택(나는 제외)
  
  * ex)$(대상요소).siblings().속성;
  
  * nextAll() : 대상요소를 기준으로 다음에 오는 모든 요소 선택
  
  * 대상요소.prev() : 대상요소를 기준으로 이전(앞)에 오는 모든 요소 선택
  
  * 대상요소.prevAll() : 대상요소를 기준으로 이전(앞)에 위치한 모든 형제요소 선택
  
  * 대상요소.first() : 가장 처음에 만들어진 해당 요소를 선택
  
  * 대상요소.last() : 가장 마지막에 만들어진 해당 요소를 선택

* 효과
  
  * animate() : 대상요소에 애니메이션 주기
  
  * 인자1 - > {스타일 속성 : 값}
  
  * 인자2 - > 속도(fast, slow)
  
  * ex) 버튼 클릭시 div 가로, 세로 400px 천천히 늘어나게 하기
    
      $(documnet).ready(function(){
    
          $("대상요소").click(function(){
    
              $(대상요소).animate({
    
                  "width" : "400px",
    
                      "height" : "400px"
    
                          }, "slow");
    
                      })
    
      })
  
  * hide(seconds) : display none 의 속성을 적용, 초(seconds) 값으로 속도 조절(1000당 1초)
    
         $("선택자").click(function(){
                 $("선택자").hide(1000);
           })
  
  * show(seconds) : display block의 속성을 적용
    
        $("선택자").click(function(){          
              $("선택자").show(1000);
              })
  
  * toggle(seconds) : hide() + show() 동시 적용
    
        $("선택자").click(function(){ 
            $("선택자").toggle(1000); })
  
  * slideDown( ) : display none 속성을 display block으로 변경
  
  * slideUp( ) : display none으로 변경

* 요소 변경
  
  * 대상요소.remove( ) : 요소 삭제 함수 -> 상위태그를 삭제하면 하위요소도 함께 삭제(모든 값 삭제)
  
  * 대상요소.empty( ) : 대상요소가 가지고 있는 모든 하위요소를 제거 (값 비우기) 

# Guide to flex

## 1. flex 란?
css3에서는 보다 편리한 레이아웃을 위해 flex를 지원한다.
flex의 contents는 어떤 방향으로든 정렬이 가능하고,
공간 내에서 크기조절 및 순서또한 사용자가 지정할 수 있다.

## 2. flex 사용법
1) 레이아웃을 구성할때 콘텐츠를 감싸는 부모요소에 flex를 지정한다.
2) 부모의 flex속성, 자식의 flex속성을 한다.

예) 코드소스 영역

## 3. flex 속성
- 부모속성 : display, flex-direction, flex-wrap, flex-flow, justify-content, align-items,align-items(부모요소), align-content
- 자식속성 : order, flex-grow, flex-shrink, flex-basis, flex, align-self, stretch, flex-start,flex-end, center, baseline, initial, inherit

###  부모에대한속성(.container)
예) [이미지] [코드예시]
> #### display
.container { display: flex;}

> #### flex-direction

.container { display: flex; 
		           flex-direction: row | row-reverse | column | column-revers
		         }
	row : 기본값으로, 행으로 수평방향으로 왼쪽에서 오른쪽으로 정렬한다.
	row-reverse : 행으로 수평방향으로 오른쪽에서 왼쪽으로 정렬한다.
	column : 열로 수직방향으로 위에서 아래로 정렬한다.
	column-reverse : 열로 수직방향으로 아래에서 위로 정렬한다.
	initial : 디폴트 값으로 이 속성을 설정한다.
	inherit : 부모 요소로부터 값을 상속 받는다.
 
> #### flex-wrap
   - wrap을 주지 않았을 경우
	    [img]
   - wrap을 줬을 경우
 	   [img]
	.container {  display: flex;   
		      flex-direction: row;
  	  	      flex-wrap: wrap;
		   }
	nowrap : 기본값으로, flexible item이 wrap 되지 않도록 지정한다.
	wrap : 만일 필요하다면 flexible item을 wrap한다.
	wrap-reverse : 만일 역순으로 flexible item을 wrap할 필요가 있을때 지정한다.
	initial : 디폴트 값으로 이 속성을 설정한다.
	inherit : 부모 요소로부터 값을 상속 받는다.
> #### flex-flow
  - flex-flow 속성은 flex-direction, flex-wrap 속성의 축약속성이다.
	flex-flow : flex-direction flex-wrap;
	.container {  display: flex;
  		           flex-flow: row wrap;
		          }
            
> #### justify-content
   - 주축 방향으로의 배치 설정
	.container {  display: flex;
		             justify-content: flex-start | flex-end | center | space-between | space-around;
		          }
            [img]
            
> #### align-items(부모요소) <-> align-self(자식요소) 
- justify-content교차 축 버전
	.container { align-items: flex-start | flex-end | center | baseline | stretch;}
          [img]
          
> #### align-content
  - item들 줄의 속성 선언.
	.container { align-content: flex-start | flex-end | center | space-between | space-around | stretch; }
   [img]


###  자식에대한속성(.items)
> #### order
  - item들의 순서 재배치 선언
    [img]
    
> #### flex-grow
 - flex-direction방향으로 item들의 width 또는 height 비율 선언
  [img]
  
> #### flex-shrink
 - 화면크기가 줄어들 때, 특정 아이템(들)이 줄어드는 변화의 비율을 선언
	.item:nth-child(3){ width: 100px;
			                  flex-shrink: 0;
			                 }
        (줄어드는 비율을 0으로 설정했고, width값을 100px로 선언했으므로 창이 줄어들어도 100px 유지)
        
> #### flex-basis
- item의 width, hright를 초기 설정 값으로 시작하고 싶을 경우 
	auto : 플렉스 기준 값으로 설정 
        양수 :  플렉스 기준 비율로 설정
        단위(px,vw,..) : 단위 길이 만큼 설정
	
	.item{ flex-basis: 100px; }
 
 
> #### flex
   - flex: flex-grow, flex-shrink, flex-basis 속성의 축약속성이다.
	.item{ flex: 1 2 20em;}
        flex-grow: 1;
        flex-shrink: 2;
        flex-basis:  20em;

> #### align-self <-> align-items(부모요소)
 -  어떤 방식으로 정렬될 것인지 지정하는 속성이며, 각 플렉스 항목에 개별적으로 적용할 수 있다.
 [img]
stretch : 컨테이너에 맞춰 모든 플렉스 항목들의 높이값이 동일하도록 조정합니다. (기본값)
flex-start : 플렉스 컨테이너의 시작 부분(왼쪽)에 위치합니다. 각 항목의 높이는 각 항목의 콘텐츠 양에 따라 결정됩니다.
flex-end : 플렉스 항목들을 컨테이너의 아래쪽으로 위치합니다.
center : 각 항목의 위 아래 잔여 공간을 동일하게 분배하기 때문에 각 항목이 수직을 기준으로 중앙에 정렬합니다.
baseline : 모든 플렉스 항목을 콘텐츠에 지정된 기준선을 중심으로 정렬합니다. 기준선은 각 항목마다 다를 수 있습니다.
initial : 이 속성의 기본값을 따릅니다.
inherit : 부모 요소로부터 값을 상속 받습니다.

### FLEX 활용 예제 SITE
- http://codepen.io/team/css-tricks/pen/jqzNZq
- http://the-echoplex.net/flexyboxes/

  
 

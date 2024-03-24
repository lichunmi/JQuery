# 준비 구문  
```javascript  
    // javascript
        window.onload = function(){
            //실행 코드
        }
        window.addEventListener('load', function(){
            //실행 코드
        })
        addEventListener("DOMContentLoaded", (event) => {
            //실행 코드
        });
        onDOMContentLoaded = (event) => {
            //실행 코드
        };
    // JQuery
        $(document).ready(function(){
            //실행 코드
        })
        $(function(){
            //실행 코드
        })
        $(window).load(function(){
            //실행 코드
        })
        $(window).on('load', function(){
            //JQuery 3x, = on 이벤트 메서드 작성시 오류 없음
            //실행 코드
        })
```

# 선택자 , 스타일  
```javascript
    // javascript
        let title = document.querySelector('h1');
        title.style.color = 'red';
    // JQuery
        let title2 = $('h2');
        title2.css('text-decoration', 'underline');

```
---
***
___   

# 랜덤번호 받기  
**소수자**  
```javascript
    Math.random();
```  
**floor->정수로 바꾸기**  
**0~6번까지-> x7**  
새로고침 할때마다 h2에 pink color 랜덤 적용
```javascript
    let num = Math.floor(Math.random() * 7);  
    $('h2').eq(num).css('color','pink');
```

# 메서드
$('h1').parent();
$('h1').parents();
$('h1').parents('선택자');
$('h1').parentsUntil('선택자');

siblings(); | 형제
next(); | 다음 요소(동생)
nextAll(); | 모든 다음요소
nextUntil('div'); | 다음 요소들 중 div까지 
prev(); | 이전 요소 (형)
prevAll(); | 이전 요소들 (형)
prevUntil('div'); | 이전 요소들 중 div까지 


children(); | 자손 요소
children('a'); | 자손 요소 a 
find('a'); | 후손 요소 a
find('> a'); | 후손에서 자손
find('+ a'); | 바로뒤 동일요소
find('~ a'); | 뒤에 모든요소  


append() | 마지막 자손으로 추가
prepend() | 첫번째 자손으로 추가
after() | 동생으로 추가
before() | 형으로 추가  

$('A')appendTo(B) | B의 마지막 자손으로 A 추가
prependTo() | 첫번째 자손으로 추가
insertAfter() | 동생으로 추가
insertBefore() | 형으로 추가    

remove() | 본인 삭제
empty() | 본인의 자송 후손 삭제
removeAttr() | 본인의 태그속성 제거  

**setTimeout, setInterval**
```javascript
        //3초뒤에 width속성 제거
       setTimeout(function(){
           $('img').removeAttr('width');
       },3000);
        //1초마다 물고기 1개 복제
       setInterval(function(){
           $('img').first().clone().appendTo('.fishbowl');
       }),1000;
```  

**html(), text()**
**attr(), prop()**
```javascript
       $('img').attr('width', 200);
       $('img').attr('width', function(index){
           return (index + 1) * 100;
       });
       $('img').attr({
           height: 200,
           width: function(index){
               return (index + 1) * 100;
           }
       })
       //attr('checked', 'checked');
       //prop('checked', true);
```

**$('선택자').addClass('클래스명');**
**$('선택자').removeClass('클래스명');**
**$('선택자').toggleClass('클래스명');**
**$('선택자').mouseenter('클래스명');**
**$('선택자').mouseleave ('클래스명');**
```javascript
       $('h1').mouseenter(function(){
           $(this).addClass('active');
       });
       $('h1').mouseleave(function(){
           $(this).removeClass('active');
       });
       $('h1').click(function(){
           $(this).toggleClass('active');
       });
```                                                                                     
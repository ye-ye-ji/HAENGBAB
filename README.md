# HAENGBAB

행복은간장밥은 빠르고 간편하면서도 건강한 음식을 제공하는 간장 소스 기반의 캐주얼 한식 브랜드입니다.<br>
디자인 컨테스트 우승작을 기반으로 메인 페이지를 구현했으며 로그인과 회원가입 페이지를 추가했습니다.

- [행복은 간장밥 홈페이지](http://www.haengbab.com/) <br>
- [행복은 간장밥 리뉴얼 페이지](http://yeji-jung.com/project/hangbab/index.html)
###### * *리뉴얼 페이지는 구글 크롬 브라우저에 최적화되어 있습니다.* ######

## 로그인 ##
#### 입력된 내용과 조건이 부합하지 않으면 하단에 설명이 나타납니다. ####
![login](https://user-images.githubusercontent.com/74514595/113678230-64607c00-96f9-11eb-8015-662705500ec3.jpg)
![con2](https://user-images.githubusercontent.com/74514595/113679050-49423c00-96fa-11eb-932d-365821acc76a.jpg)

    $('#loginForm').submit(function(){
            if( $('#userEmail').val() == "" ){ 
                $('#email-msg').css('display','block').html('이메일을 입력 하세요');
            }else{
                $('#email-msg').text('').css('display','none'); 
            }

            if( $('#userPwd').val() == "" ){ 
                $('#pw-msg').css('display','block').html('비밀번호를 입력 하세요');
            }else if( $('#userPwd').val().length < 4 ){ 
                $('#pw-msg').css('display','block').html('비밀번호는 4자 이상');         
            }else{
                $('#pw-msg').text('').css('display','none'); 
            }
            return false;
        }); 

## 회원가입 - 약관동의 ##
#### 내용 보기를 클릭하면 상세설명이 아래로 슬라이드 되어 나타납니다. 전체동의 체크박스를 클릭하면 하단의 체크박스가 동시에 체크됩니다. ####

![join](https://user-images.githubusercontent.com/74514595/113680211-8e1aa280-96fb-11eb-8755-548012ca89e6.jpg)

    var viewBtn = $('.agree-wrap .view');
    
    viewBtn.click(function(e){
        e.preventDefault();
        if( $(this).parent().parent().hasClass('open') ){
            $(this).parent('div').parent('li').removeClass('open');
            $(this).parent('div').next('.policies').slideUp();
        }else{
            $(this).parent('div').parent('li').addClass('open');
            $(this).parent('div').next('.policies').slideDown();
        }
    });
    
    $('#agreeAll').click(function(){
            chkAll(); 
        });

    function chkAll(){
        var chk = $('#agreeAll').is(':checked');

        if(chk) { 
            $('input[type=checkbox]').prop('checked', true);
        }else{
            $('input[type=checkbox]').prop('checked', false); 
        }    
    }

## 회원가입 - 정보입력 ##
#### 입력된 내용과 조건이 부합하지 않으면 하단에 설명이 나타납니다. ####

![jjoin](https://user-images.githubusercontent.com/74514595/113694666-00df4a00-970b-11eb-91d8-7f61d39778f8.jpg)


    $('#joinForm').submit(function(){
        if( $('#userId').val() == "" ){ 
            $('#id-msg').css('display','block').html('아이디를 입력 하세요');
        }else{
            $('#id-msg').text('').css('display','none'); 
        }
        
        if( $('#userPwd').val() == "" ){
            $('#pw1-msg').css('display','block').html('비밀번호를 입력 하세요');
        }else if( $('#userPwd').val().length < 8 ){ 
            $('#pw1-msg').css('display','block').html('비밀번호는 8자 이상');         
        }else{
            $('#pw1-msg').text('').css('display','none');
        }

        if( $('#userPwd').val() != $('#userPwdConfirm').val() ){ 
            $('#pw2-msg').css('display','block').html('비밀번호가 일치하지 않습니다');   
        }else{
            $('#pw2-msg').text('').css('display','none'); 
        }
        
        if( $('#phoneNumber').val() == "" ){ 
             $('#pnum-msg').css('display','block').html('연락처를 입력 하세요');   
        }else{
            $('#pnum-msg').text('').css('display','none'); 
        }

        if( $('.email-rcv:checked').length == 0 ){
           $('#email-rcv-msg').css('display','block').html('수신여부를 선택하세요');   
        }else{
            $('#email-rcv-msg').text('').css('display','none'); 
        }
  
        return false;
    });

## 회원가입 - 가입완료 ##

![logincomp](https://user-images.githubusercontent.com/74514595/113680345-b4d8d900-96fb-11eb-93df-b9d39788593a.jpg)


## 디자인 저작권 ##
##### 메인 페이지에 사용된 디자인은 라우드 소싱 사이트 내의 콘테스트 우승작입니다. #####
행복은 간장밥 디자인 콘테스트 : https://www.loud.kr/contest/view/29464 <br>
우승작 디자이너 디자인 맛집(webdy) 사이트 : https://www.loud.kr/m/webdy#portfolio

###### * *비영리 목적으로 저작물을 사용했으며 어떠한 상업적 용도로도 사용하지 않았습니다.* ######

##### [리뉴얼 페이지](http://yeji-jung.com/project/hangbab/index.html) 에 직접 방문해보세요. #####

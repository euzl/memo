# 파이썬 정리(C++과의 차이를 중점으로)
파이썬을 공부하며 C++과 다르거나 헷갈리는 개념 위주로 정리하고자 함
            
           
### 주석
'#'기호사용
        
          
### 입력 및 출력

    name = input()     # 값을 입력받을 수 있다.
    print(name)        # name에 저장된 값 출력
    name = input('What your name?')   # What your name? 이라고 물어보면 입력할 수 있다.
    print('Hi ', name)                # Hi 라는 문자열과 함께 출력

     
           
### 타입 변환 및 확인
    i = 42
    type(i)      # int 반환
    j = 1.5
    type(j)      # float
    j = int(j)   # int 형으로 바뀜
    type(j)      # int 반환
    print(j)     # '1' 출력

 - type(<변수명>) -> 타입 반환 
 - float(<변수명>) -> 타입 변환 // float, int 등.  단, 변환이 될 때만! str에서 int 는 변환 불가!
          
               
### 들여쓰기
- 들여쓰기 = [Tab] = [Space]*4번
- C++에서 {...} 대신 들여쓰기를 사용함
- 들여쓰기가 제대로 되지 않으면 조건에 해당하는 코드를 실행시키지 않거나 error 발생
         
           
### 조건문(if, else)
    if <조건> :            # 콜론(:) 필수!!
    <들여쓰기>실행할 코드    # 들여쓰기 필수!!


~ 추가추가 ~ 

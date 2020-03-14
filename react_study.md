> VELOPERT님의 [\[React.JS기초강의\]](%5Bhttps://velopert.com/reactjs-tutorials%5D%28https://velopert.com/reactjs-tutorials%29) 를 보고 공부하면서 기억해야할 키워드 위주로 정리<br>
> (순서 아~~무 의미 없음!)

## 1. Virtual DOM 사용
**라이브러리 || 프레임워크 :** <br>
DOM 관리, 상태값 업그레이드 관리 최소화 + 기능개발, UI에 집중하도록<br>
ex) Angular, Ember, Vue, React 등. 각각의 철학과 추구하는 방향이 다름<br>

프레임워크들은 패턴으로 이뤄져있음
|이름| 설명 |
|:--:|--|
| MVC | 데이터단을 담당하는 Model <br> 사용자의 화면에서 보여지는 View <br> 사용자가 발생시키는 이벤트를 처리하는 Controller |
| MVVM | MVC에서 파생 (View Model) |
| MVW | MVC에서 파생 (Whatever) |

프레임워크들의 모델은 대부분 양방향 바인딩을 통해 Model 값이 변하면 <br>
-> View에서도 **변화시켜준다.** (`변화`에 따라 필요한 곳만!)
<br>
<br>
변화는 어떻게 진행되는가?<br>
특정 event 발생 -> Model 변화 -> 어떤 DOM을 가져와 어떤 방식으로 View 업뎃할지 로직 정해야 됨. 

🤔페북 왈. 그냥 View를 새로 만들자!<br>
**Virtual DOM사용!** <br>
-> 일단 바뀐 데이터로 그린다음 이전상태와 비교해서 바뀐부분만 바꾸기. (DOM 변화를 최소화해주는 역할)
<br>
<br>
## 2. 리액트 프로젝트 만들기
- `create-react-app`사용합시다

- 리액트 프로젝트는 컴포넌트를 여러 파일로 분리해서 저장한다.
	- 컴포넌트는 JSX로 작성됨. (Bable 사용)
	- 여러파일을 한 개로 결합하는건 Webpack을 사용

- 설치 (MAC)
	```
	npm install -g create-react app
	create-react-app hello-react
	```
	/Users/euzl/ 의 하위폴더 `hello-react`로 생성 (위에서 설정한 이름)
- 실행 (MAC)
	```
	cd hello-react
	yarn start
	```
- `App.js` 는 컴포넌트에 해당하는 코드. (함수형과 클래스형으로 나뉜다. 차이는 4번에서~)
	- `import` 작업 : webpack 덕분에 가능
	- ⭐️클래스형태의 컴포넌트에는 꼭 render 함수(내부에서 JSX를 return하는) 필요
	- `export default App;` : 우리가 만든 컴포넌트 내보내기
	- `import App from './App';` : 우리가 만든 컴포넌트 불러오기
<br><br>
## 3. JSX
- 두 개 이상의 엘리먼트는 무조건 하나의 엘리먼트로 감싸져 있어야 함
	- ex
	```jsx
	<div>
	hello
	</div>
	<div>
	bye
	</div>
	```
	는 에러 ~~~
	```jsx
	<Fragment>
		<div>
		hello
		</div>
		<div>
		bye
		</div>
	</Frament>
	```
	는 괜춘 ~ 이 때, Fragment 말고 div라 해도 괜찮지만,, Fragment를 더 추천
- 자바스크립트 값 사용하려면? `{<변수명>}`
- 조건부렌더링 하려면? 삼항연산자 or AND 연산자
	- if사용불가. IIFE대체사용
- 화살표함수 : this, arguments, super 개념이 없는 익명함수 `( ) => { <내용> }`
<br><br>
### (참고) 자바스크립트 변수선언 관련
- const : 한번 선언하고 변하지 않는 값
- let : 변하는 값<br> -> 볼록 단위(`{  }`)로 적용
- var : 함수 단위로 적용. const와 비슷. 근데 ES6에선 쓸 일 없습니다.
<br><br>
## 4. Props VS State
리액트 컴포넌트에서 데이터는 Props와 State
- Props : 부모가 자식에게 주는 값. default 설정가능.
- State : 컴포넌트 내부에 선언. 내부에서 값 변경가능.
<br><br>
### 컴포넌트 (함수형 / 클래스형)
주요차이는 함수형엔 State, LifeCycle이 빠져있다.<br>
그래서 조금 더 간단! 성능차이는 엄청나진않음.
<br>
state에 대해 적을 예정이므로 함수형 컴포넌트겠쥬 ?
<br>
`this.setState`이 함수가 호출되면 컴포넌트가 리렌더링 되도록 설계되어있다. (**State값을 바꾸기 위해 무조건 거쳐야 됨**)
<br><br>
### ⭐︎리액트에서 이벤트함수 설정할 때 주의사항
- 이벤트 이름은 camelCase 
	ex) onClick, onMouseDown, ...
- 이벤트에 전달해주는 값은 함수여야 함. (메소드를 호출하지 말 것!!)
	ex) `<button onClick = {this.handleIncrease}>+</button>`
		this.handleIncrease() 가 아닌것 집중
    




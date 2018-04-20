# Front end dev blog

# 자바스크립트의 언어적 개념
1. 객체란
- 객체란: 프로퍼티(key, value)의 집합
- 인스턴스: 오브젝트를 사용해서 새로 생성한 오브젝트를 인스턴스라고 하며, new연산자로 생성할 수 있다.
- 인스턴스를 생성하는 목적: 인스턴스마다 다른 값을 유지, 제어하기 위해 인스턴스를 생성. 즉, 원본을 유지하고 복사한 내용의 값을 변경해서 사용하기 위해 생성.

2. 빌트인
- 빌트인이란: 렌더링 단계에서 js가 오브젝트를 생성하고 값을 초기화하며 연산자를 설정하는데 이 단계에서 만드는 것을 총칭하여 빌트인이라고 한다. 크게 연산자, 데이터타입, 오브젝트로 나누어진다.

```
- 빌트인 연산자: +, -, *, /, %, ++, --, !, !==, /= 등
- 빌트인 데이터타입: undefined, null, boolean, number, string
- 빌트인 오브젝트: Global, Object, Function, Array, String, Boolean, Number | Math, Date, RegExp, JSON, Error 
```

3. JS가 오브젝트를 인식하는 방법
- 처리할 데이터 타입을 보고 사용할 오브젝트를 선택
- 파라미터로 넘겨 줄 데이터릴 준비
- 데이터 타입에 따라 오브젝트를 생성
- 오브젝트.메소드() 형태로 호출하면서 연결하려는 값을 파라미터로 넘겨줌
e.g: Array_object.concat([sports', 'soccor', '11'])
result: [sports', 'soccor', '11']
- 메소드가 실행되며 메소드에서 값을 반환 

4. prototype 오브젝트
- JS에서는 prototype을 사용하여 메소드를 구분한다. 
(prototype으로 감싸진 것은 메소드, 아닌 것은 프로퍼티. 아래 코드 참조)

```
String: {
  length: 값,
  prototype: {
    concat: function() {}
    indexOf: function() {}
  }
}
```
- prototype은 이 외에도 다른 오브젝트를 상속받아 연결하거나 prototype에 연결된 프로퍼티를 공유할 때 사용한다. (뒤에서 다시 다룸)

5. new 연산자
- new연산자는 constructor위치에 지정한 생성자를 호출하여 새로운 오브젝트를 생성하여 반환한다. 반환된 오브젝트를 인스턴스라고 한다.
- constructor 위치에는 빌트인 오브젝트 생성자(String, Array, Function등)를 지정할 수 있다.
- new연산자로 인스턴스를 생성하면 원본 오브젝트의 prototype에 연결된 메소드를 인스턴스에서 공유한다. 여기서 공유는 복사가 아닌 참조(reference)를 의미한다. 즉, 인스턴스.메소드()로 호출하면 원본 오브젝트의 prototype에 연결된 메소드가 호출된다.
- 빌트인 오브젝트의 메소드는 기능이 정해져 있으며 다른 곳에서 사용하므로 기능을 바꿔서는 안된다!
- fallback메소드: es5를 지원하지 않는 브라우저에서 es5에 추가된 메소드를 사용하기 위해 빌트인 오브젝트의 prototype에 연결한 메소드를 fallback메소드라고 한다.

6. constructor
- constructor가 있어야 새로운 오브젝트를 생성할 수 있다.
- Global, Math, JSON 오브젝트에는 constructor가 없다. 즉, 인스턴스를 생성할 수 없다.
- instanceof 연산자는 지정한 오브젝트로 생성한 인스턴스이면 true, 아니면 false를 반환한다
```
인스턴스 instanceof 오브젝트
```

# Object 오브젝트
- es3 기준 Object 오브젝트의 프로퍼티 리스트
```
| 이름                    | 개요                                 |
|------------------------|-------------------------------------|
| Object                 |                                     |
| new Object()           | 인스턴스 생성                          |
| Object()               | 인스턴스 생성, new Object()와 같음       |
| Object.prototype       |                                     |
| constructor            | 생성자                                |
| toString()             | 문자열 표시 변환                        |
| toLocalString()        | 지역화 문자열로 변환                     |
| valueOf()              | 프리미티브 값 반환                      |
| hasOwnProperty()       | 프로퍼티 소유 여부 반환                  |
| isPrototypeOf()        | Prototype에 오브젝트 존재 여부 반환       |
| propertyIsEnumerable() | 프로퍼티 열거 가능 여부 반환               |
```
- es5 기준 Object 오브젝트의 프로퍼티 리스트
```
| 이름                    | 개요                                 |
|------------------------|-------------------------------------|

```
- es5 스펙에서 아래와 같이 오브젝트를 분류하고 있다
  * 오브젝트: 0개 이상의 프로퍼티로 구성된 기본 형태
  * 빌트인 오브젝트: 렌더링 과정에서 JS가 생성하는 오브젝트를 의미
  * 네이티브 오브젝트: Argument 오브젝트와 같이 JS 프로그램을 실행할 떄 생성되는 오브젝트
  * 호스트 오브젝트: JS 실행환경을 보완, 지원하기 위해 호스트 환경에서 제공하는 오브젝트를 의미. 네이티브 오브젝트를 제외한 오브젝트가 대상
  e.g: DOM에서 제공하는 NodeList 오브젝트가 이에 해당


```

```





나중에 footer에 출처 쓰기..


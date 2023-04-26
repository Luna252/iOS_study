# Basic - Variable, Type, Constant

## 1️⃣ **변수(Variable)**
- 프로그램 데이터를 저장하는 공간
- `var` 키워드로 선언
- 변수 할당과 변경
    ```swift
    var str = "Hello, World"
    // 새로운 변수 str에 "Hello, World"라는 문자열 저장(할당)

    str = "Hello, Swift"
    // 이미 존재하는 변수 str의 값을 "Hello, Swift"로 변경
    ```
<br>

## 2️⃣ **Type**

- 타입은 변경이 불가하다.
1. String
    - 문자열을 나타내는 타입
    - `""` 안에 데이터를 입력한다.
    ```swift
    var str = "string"
    ```

2. Integer
    - 정수를 나타내는 타입
    ```swift
    var age = 20
    ```

3. Double
    - 소수를 나타내는 타입
    ```swift
    var score = 9.9
    ```

4. Booleans
    - 참, 거짓을 표현하는 타입
    - `true` , `false` 의 값을 가진다.
    
    ```swift
    var isEnabled = false
    ```
<br>    

## 3️⃣ **String Interpolation**

- 데이터를 문자열로 표현.
- `\(변수)` 로 표현
    ```swift
    var score = 100
    
    var text = "Your score is \(score)"
    
    // "Your score is 100 "
    ```
<br>

## 4️⃣ **상수(Constant)**

- 변수와 같이 프로그램 데이터를 저장하는 공간
- `let` 키워드로 선언
- 변수와는 달리 할당된 값을 변경할 수 없다.
    ```swift
    let name = "Luna"
    // name = "Kim" 으로 변경이 불가하다. (에러발생)
    ```

<br>

## 5️⃣ **Type Annotation**

- 변수 선언시 타입을 명시할 수 있다.

    ```swift
    // 타입을 명시하지 않는 경우. 타입추론(Type inference)
    var weeks = 10
    var token = "qwer1234"

    // 타입을 명시하는 경우
    var days: Int = 5
    var userName: String = "Jake"
    ```
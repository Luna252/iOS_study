# 함수 (function)

- 특정 태스크를 수행하기 위한 코드 블록
- 만들어 놓은 함수를 다시 사용할 수 있다 → 효율적으로 코드 작성 가능

## 👉 **function 작성**

- `func` 키워드를 이용해서 작성
- `func [함수이름](파라미터)`

```swift
// 함수 작성
func printHello() {
		print("Hello, world")
}

// 함수 실행
printHello()
```
<br>

## 👉 **Input, Output**

- 파라미터를 통해 외부에서 Input을 받아 함수 내부에서 사용가능하다.
- `return` 키워드를 통해 output을 외부로 전달 가능하다.

```swift
// ---input---
func printName(name: String) {
		print("name is \(name)")
}

printName(name: "Luna") // "name is Luna"

// ---output---
func makeDouble(num: Int) -> Int {
		return num * 2
}

let result = makeDouble(num: 3)
print(result) // 6
```
<br>

## 👉 **input parameter label**

- input parameter의 이름을 외부, 내부에서 각각 다르게 사용할 수 있다.
    
    → 코드의 가독성을 높여준다.
    
    - `func [함수이름](외부이름 내부이름:타입) {}`
    
    ```swift
    func printName(of name: String) {
    		print("name is \(name)")
    }
    
    printName(of: "Luna") // "name is Luna"
    ```
    
    - 외부 파라미터를 생략하고 싶은 경우 → `_`
    
    ```swift
    func printName(_ name: String) {
    		print("name is \(name)")
    }
    
    printName("Luna") // "name is Luna"
    ```
    
<br>

## 👉 **default parameter**

- 파라미터에 기본값을 설정할 수 있다.

```swift
// 파라미터 ratio에 0.2라는 기본값을 설정.
func discount(price: Double, ratio: Double = 0.2) -> Double {
		return price * (1 - ratio)
}

// price만 입력, ratio는 기본값으로 함수실행
let result1 = discount(price: 2000)
print(result1) // 1600

// 기본값을 무시하고 입력가능
let result2 = discount(price: 2000, ratio: 0.5)
princ(result2) // 1000
```
<br>

## 👉 **variadic function**

- 파라미터의 개수를 제한없이 받을 수 있는 함수형태
- `print()` 함수도 해당된다.
- 외부에서 들어온 여러개의 파라미터를 내부에서는 배열의 형태로 받는다.

```swift
func printNames(_ names: String...) {
		for name in names {
				print("name is \(name)")
		}
}

printNames("Kim", "Park", "Shin")
// name is Kim
// name is Park
// name is Shin
```
<br>

## 👉 **throwing function**

- 에러 등의 예외상황을 처리하는 함수
- `throws` 키워드로 예외사항을 만든다.
- `throws` 가 있는 함수는 `try` 로 호출, `do-catch` 로 에러감지

```swift
enum DiviedError: Error {
		case cannotZero
}

func divide(dividend: Int, divisor: Int) throws -> Int {
		if divisor == 0 {
				throw DivideError.cannotZero
		}
		return Int(divided / divisor)
}

do {
		let result = try divide(dividend: 80, divisor: )
		print(result)
} catch {
		print(error.localizedDescription)
}
// throws로 설정한 대로 divisor가 0으로 입력되었기 때문에 에러감지.
```
<br>

## 👉 **inout parameter**

- 기본적으로 외부에서 입력된 Input parameter는 상수이기 때문에 함수 내부에서 변경 불가.
- `inout`  키워드를 이용하면 내부에서 변경이 가능하다.
- 함수호출시 파라미터값에 `&` 을 붙여준다.
```swift
func makeTriple(num: inout Int) {
		num *= 3
}

var num = 8
makeTriple(num: &num)

print(num) // 24
```
# Conditions
## 1️⃣ **조건문 conditions**

- `if` 를 이용해서 조건에 따라 다른 프로그램이 실행 되도록 할 수 있다.

```swift
let num1 = 3
let num2 = 5

let sum = num1 + num2

if sum > 10 {
	print("over 10")
} else {
	print("not over 10")
}
```

## 2️⃣ **combining conditions**

- 조건문이 여러개인 경우
- `&&`  : 조건을 모두 충족해야 true (and)
- `||`  : 조건을 하나라도 충족하면 true (or)

```swift
let age1 = 25
let age2 = 15

if age1 > 20 && age2 > 20 {
		print("모두 성인 입니다.")
} else {
		print("미성년자가 포함되어있습니다.")
}

if age1c > 20 || age2 > 20 {
		print("20세 이상 보호자가 있으므로 출입이 가능합니다.")
} else {
		print("20세 이상 보호자가 있어야 출입이 가능합니다.")
}
```

## 3️⃣ **삼항 연산자 ternary operator**

- 조건문을 간단하게 변수에 할당이 가능하다.
- `let [변수] = [조건] ? [true일 경우의 값] : [false일 경우의 값]`

```swift
let age3 = 30
let age4 = 40

let text = age3 == age4 ? "same" : "not same"
```

## 4️⃣ **switch statement**

- `switch-case` 형태의 조건문
- 조건의 모든 케이스가 커버되도록 작성해야한다.
- enum과 함께 사용하기 좋다.
 ```swift
enum Direction {
    case up
    case down
    case left
    case right
}

let direction = Direction.down

switch direction {
case .up:
    print("up")
case .down:
    print("down")
case .left:
    print("left")
case .right:
    print("right")
}
```
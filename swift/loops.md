# Loops
## **반복문 loops**

- 특정 코드를 반복해서 수행할 수 있는 메커니즘

## 1️⃣ **for loops**

- array, range와 같은 주어진 범위를 돌면서 코드를 반복 수행할 수 있다.

```swift
// Range
let numRange = 1...10 

for num in numRange {
	print("num is \(num)")
}

// Array
let names = ["John", "Kevin", "Jason"]

for name in names {
	print("name is \(name)")
}
```

## 2️⃣ **while loops**

- 특정 조건을 만족할때 까지 코드를 반복 수행한다.

```swift
var num1 = 1 

while num1 <= 20 {
	print(num1)
	num1 += 1
}

print("20에 도달했습니다.")
```

## 3️⃣ **repeat loops**

- 특정 조건을 만족할때 까지 코드를 반복 수행한다.
    - `while loops` : 조건을 먼저 체크하고 수행
    - `repeat loops` : 코드를 수행하고 조건을 체크

```swift
var num2 = 1 

repeat {
	print(num2)
	num2 += 1
} while num2 <= 20 // 20보다 작거나 같으면 반복 수행.

print("20에 도달했습니다.")
```

# 중단/건너뛰기

## 1️⃣ **exiting loop**

- 반복문을 중단시키는 `break` 키워드를 사용한다.

 

```swift
// 0~3까지의 정수가 출력된다.

for i in 0...10 {
    if i == 4 {
        break
    }
    print(i)
}
```

## 2️⃣ **skipping items**

- 특정 조건을 건너뛰고 싶은 경우 `continue` 키워드를 사용한다.
```swift
// 0~10까지의 정수를 출력하되, 4는 제외하고 출력하라.

for i in 0...10 {
    if i == 4 {
		   continue   
    }
    print(i)
}
```
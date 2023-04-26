# Basic - Collections Types

## **Collection Types**

- 데이터의 집합
- 변수, 상수로 생성 가능하지만, 변경할 필요가 없는 컬렉션이라면 상수로 생성하는 것이 컬렉션 성능을 더욱 최적화한다. (코드에 대해 쉽게 추론)
---
## 1️⃣ **Array**

- 여러 데이터를 순서대로 담아 놓은 변수
- `[]` 를 이용해서 선언
- 순서대로 데이터에 index 부여, index로 접근 가능 (0부터 시작하는 숫자)
    ```swift
    let mon = "Monday"
    let tue = "Tuesday"
    let wed = "Wednesday"
    let thu = "Thursday"
    let fri = "Friday"
    let sat = "Saturday"
    let sun = "Sunday"

    // array
    let weeks = [mon, tue, wed, thu, fri, sat, sun]

    // 인덱스로 접근
    weeks[0] // Monday
    weeks[6] // Sunday

    // Empty array 선언
    var emptyArr01: [Int] = []

    var emptyArr02 = [Int]()
    ```

## 2️⃣ **Dictionary**
- 여러 데이터를 Key : Value 형태로 담아 놓은 변수
- Key를 통해 접근 가능
    ```swift
    // dictionary
    let languageCode = [
            "한국" : "ko",
            "미국" : "en",
            "일본" : "ja",
    ]

    // Key로 접근
    languageCode["한국"] // "ko"
    languageCode["중국"] // nil (존재하지 않는 값)

    // Empty Dictionary
    var emptyDic01: [String: Any] = [:]

    var emptyDic02 = [String: Any]()
    ```

## 3️⃣ **Set**
- 여러 데이터를 랜덤순서로 중복없이 담아 놓은 변수
- `Set<Int>` 를 명시하지 않으면 array로 타입추론해버린다.
- Set 데이터의 타입은 작성하지 않아도 된다.
    ```swift
    // set
    var primes01: Set<Int> = [1, 2, 3, 4]
    var primes02 = Set<Int>([1, 2, 3, 4])

    var primes03: Set = [1, 2, 3, 4]
    var primes04 = Set([1, 2, 3, 4])
    // 중복된 데이터를 할당해도 자동으로 필터링.

    // Empty Set
    var emptySet01: Set<Int> = []
    var emptySet02 = Set<Int>()
    ```

## 4️⃣ **Tuple**
- 여러 데이터를 하나의 값으로 담아 놓은 변수
- 포지션(인덱스), 이름(키 값)으로 데이터 값에 접근 가능
    ```swift
    // tuple
    var phone = (os: "iOS", model: "iPhone13")

    // 포지션으로 접근
    phone.0 // "iOS"

    // 이름으로 접근
    phone.model // "iPhone13"
    ```

- 이름없이 값만으로도 생성가능 (raw value)
    ```swift
    var rawPhone = ("iOS", "iPhone13")

    rawPhone.0 // "iOS"
    rawPhone.1 // "iPhone13"
    ```

## 5️⃣ **Enum**
- 서로 관계있는 값들을 모아서 공통 유형을 정의. (열거형)
    ```swift
    // enum
    enum WeekDay {
            case mon
            case tue
            case wed
            case thu
            case fri
    }
    // case mon, tue, wed, thu, fri 로 한줄에 나타낼 수도 있다.

    // 변수에 enum WeekDay의 mon을 할당
    var today01: WeekDay = .mon // mon
    var today02 = WeekDay.mon // mon
    ```

- 연관된 값(associated value)을 가지고 있는 형태로 표현
    ```swift
    enum MediaType {
            case audio(String)
            case video(String)
    }

    // 변수에 enum mediaType의 값을 할당 + 별도의 값을 추가적으로 할당(세부데이터)
    var mp3: MediaType = .audio("mp3") // audio("mp3")
    var h264: MediaType = .video("h264") // video("h264")
    ```

- enum을 표시할 때, value를 할당해서 표현
    ```swift
    // raw value : Int
    enum MasterLevel: Int {
            case beginner
            case intermediate
            case professional
    }

    var pro = MasterLevel(rawValue: 2) // professional


    // raw value : String
    enum Direction: String {
            case up
            case down = "ddd"
    }

    var up = Direction(rawValue: "up") // up
    var down = Direction.down
    down.rawValue // "ddd"
    ```
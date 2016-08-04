# Swift 견학(A Swift Tour)

<!-- Tradition suggests that the first program in a new language should print the words “Hello, world!” on the screen. -->
전통적으로 새로운 컴퓨터 연어의 첫 번째 프로그램은 화면에 “Hello, world”라는 두 단어를 인쇄하는 것입니다.
<!-- In Swift, this can be done in a single line: -->
Swift에서는, 이를 코드 단 한 줄로 구현할 수 있습니다:

``` swift
print("Hello, world!")
```

<!-- If you have written code in C or Objective-C, this syntax looks familiar to you—in Swift, this line of code is a complete program. -->
만약 여러분이 C나 Objective-C으로 코드를 작성해본 적이 있다면, 여러분에게 이 문법(syntax)은 친숙하게 보일 겁니다 -  Swift에서, 이 코드 (한) 줄은 완전한 프로그램입니다.
<!-- You don’t need to import a separate library for functionality like input/output or string handling. -->
입/출력 또는 문자열을 다루는 것과 같은 ‘컴퓨터의 모든 기능(functionality)’을 위하여 개별적인(separate) 라이브러리를 임포트(import)할 필요는 없습니다.
<!-- Code written at global scope is used as the entry point for the program, so you don’t need a main() function. -->
전역 범위(Global scope)로 쓰여진 코드는 그 프로그램을 위한 진입점(entry point)로 사용되므로, 여러분은 `main()` 함수를 사용할 필요가 없습니다.
<!-- You also don’t need to write semicolons at the end of every statement. -->
또한 모든 문장 끝에 세미콜론(번역자 주: 즉 ;)도 쓸 필요도 없습니다.

---
<!-- This tour gives you enough information to start writing code in Swift by showing you how to accomplish a variety of programming tasks. -->
이 견학(tour)은 여러분에게 다양한 ‘프로그램을 짤 과제(programming task)’들을 수행하는 방법을 보여줌으로써 Swift으로 코드 작성을 시작하기 위한 충분한 정보를 제공하고자 합니다.
<!-- Don’t worry if you don’t understand something—everything introduced in this tour is explained in detail in the rest of this book. -->
이해하지 못 하는 것이 있다고 해서 걱정하지 마세요—이 견학에서 소개하는 모든 것들은 이 책의 나머지 부분에서 상세히 설명할 것입니다.

<!-- NOTE -- >
> 주의(NOTE):
<!-- For the best experience, open this chapter as a playground in Xcode. Playgrounds allow you to edit the code listings and see the result immediately. -->
> 가장 좋은 경험을 하기 위해서는, Xcode 안에 있는 Playground으로 이 장을 열어보세요. Playground는 여러분들에게 코드를 수정하는 즉시 그 결과를 볼 수 있게 해줄 것입니다.
> <a href="https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.playground.zip">Playground 다운 받기</a>

## 간단한 값들(Simple Values)

<!-- Use `let` to make a constant and `var` to make a variable. -->
`let`을 사용해서 상수(constant)를 만들고 `var`을 사용하여 변수(variable)를 만듭니다.
<!-- The value of a constant doesn’t need to be known at compile time, but you must assign it a value exactly once. -->
상수의 값은 컴파일 할 때에 알 필요가 없지만, 그러나 여러분은 정확하게 한번만 그 값을 부여(assign)해야 합니다.
<!-- This means you can use constants to name a value that you determine once but use in many places. -->
이는 여러분이 상수를 사용하여 특정 값에 이름을 붙인다는 것은 한번 그렇게 결정하면 여러 곳에서 이를 사용한다는 것을 의미합니다.

``` swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

<!-- A constant or variable must have the same type as the value you want to assign to it. -->
상수나 변수는 여러분이 그것들에게 부여하기 원하는 값과 같은 타입(type)을 가져야 합니다.
<!-- However, you don’t always have to write the type explicitly. -->
그러나, 그 타입을 항상 명시적으로 작성할 필요는 없습니다.
<!-- Providing a value when you create a constant or variable lets the compiler infer its type. -->
여러분이 상수나 변수를 생성할 때 제공한 값을 통해 컴파일러는 해당 값의 타입을 추정(infer)합니다.
<!-- In the example above, the compiler infers that ‘myVariable’ is an integer because its initial value is an integer. -->
위의 예에서, `myVariable`은 처음 값이 정수였기 때문에 컴파일러는 그것을 정수라고 추정합니다.

---
<!-- If the initial value doesn’t provide enough information (or if there is no initial value), specify the type by writing it after the variable, separated by a colon. -->
만약 그 처음 값이 충분한 정보를 제공하지 못 한다면(또는 처음 값이 존재하지 않는다면), 그 변수 뒤에, 콜론으로 분리하여, 그 타입을 써줘야 합니다.

``` swift
let inplicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double  = 70
```

> 실험(EXPERIMENT):
<!-- Create a constant with an explicit type of Float and a value of `4`. -->
> 명확한(explicit) `Float` 타입이면서 `4`라는 값을 가진 상수를 생성해 보세요.

<!-- Values are never implicitly converted to another type. -->
값들을 결코 절대로(implicitly) 다른 타입으로 바꿀 수 없습니다.
<!-- If you need to convert a value to a different type, explicitly make an instance of the desired type. -->
만약 여러분들이 특정값을 다른 타입으로 바꿀 필요가 있다면, 명확하게 의도한 타입의 인스턴스(instance)를 만들어야 합니다.

``` swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```
> 실험(EXPERIMENT):
<!-- Try removing the conversion to `String` from the last line. What error do you get? -->
> 마지막 줄에서 `String` 타입으로 변환하는 부분을 제거해보자. 어떤 에러가 발생하는가?

<!-- There’s an even simpler way to include values in strings: Write the value in parentheses, and write a backslash (\) before the parentheses. For example: -->
문자열들 안에 값들을 포함하는 더 쉬운 방법이 있습니다: 괄호 안에 그 값을 쓰고 그 괄호 앞에 백슬래시(\)를 쓰면 됩니다. 예를 들면 다음과 같습니다:

``` swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```

> 실험(EXPERIMENT):
<!-- Use `\()` to include a floating-point calculation in a string and to include someone’s name in a greeting. -->
> `\()` 를 이용해 문자열 안에 ‘실수형(floating-point)’ 계산을 포함하도록 해보고, 인사말 안에 누군가의 이름을 넣어보자.

<!-- Create arrays and dictionaries using brackets ([]), and access their elements by writing the index or key in brackets. -->
배열(array)과 딕셔너리(dictionary)는 대괄호([])를 이용해 생성하고, 그리고 그 대괄호 안에 인덱스(index)나 키(key)를 써서 (배열과 딕셔너리의) 각 요소을 입출력한다.
<!-- A comma is allowed after the last element. -->
콤마(번역자 주: 즉 ,)은 맨 마지막 요소 뒤에 허락된다.

``` swift
var shoppingList = ["catfish", "water", "tulips", "blue paint"]
shoppingList[1] = "bottle of water"

var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

<!-- To create an empty array or dictionary, use the initializer syntax. -->
빈 배열이나 빈 딕셔너리를 생성하려면, (다음과 같이) 초기화(initializer) 문법을 사용하면 됩니다.

``` swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```

<!-- If type information can be inferred, you can write an empty array as [] and an empty dictionary as [:]—for example, when you set a new value for a variable or pass an argument to a function. -->
만약 타입 정보를 추론할 수 없다면, 여러분은 빈 배열을 []로 쓰고, 빈 딕셔너리을 [:]로 쓸 수 있습니다—예를 들어, 여러분이 어떤 변수에 새로운 값을 할당하거나 또는 함수에 인자(argument)로 전달할 때 다음과 같이 한다.

``` swift
shoppingList = []
occupations = [:]
```

## 흐름 제어(Control Flow)
<!-- Use `if` and `switch` to make conditionals, and use `for-in`, `for`, `while`, and `repeat-while` to make loops. -->
`if`와 `switch`를 사용해서 조건문을 만들 수 있고, `for-in`, `for`, `while`, `repeat-while`을 사용해서 반복문(loops)을 만들 수 있습니다.
<!-- Parentheses around the condition or loop variable are optional. -->
조건문과 반복문을 괄호로 감싸는 것은 선택사항(optional)입니다.
<!-- Braces around the body are required. -->
중괄호({,})로 (조건문과 반복문의) 본체(body)를 감싸는 것은 필수입니다.

``` swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore)
```
In an `if` statement, the conditional must be a Boolean expression—this means that code such as `if score { ... }` is an error, not an implicit comparison to zero.
`if`문장 안에서, 조건문은 꼭 불리언(Boolean) 표현이어야 합니다—이는 `if score {...}`와 같은 코드가 에러라는 라고 표현하면 0과의 비교를 암시하지 않기 때문에 에러가 발생합니다.

---
<!-- You can use `if` and `let` together to work with values that might be missing. -->
여러분들은 빠져 있을 수도 있는 값들을 가지고 작업하기 위하여 `if` 그리고 `let`을 함께 사용할 수 있습니다.
<!-- These values are represented as optionals. -->
이러한 값들은 옵션널(optionals)이라고 표현됩니다.
<!-- An optional value either contains a value or contains `nil` to indicate that a value is missing. -->
옵션널한(optional) 값이란 어떤 값을 갖고 있거나, 또는 값이 빠졌있다는 것을 지시하고 있는 `nil`을 갖고 있거나 둘 중 하나 입니다.
<!-- Write a question mark (`?`) after the type of a value to mark the value as optional. -->
그 값이 옵션널하다고 표시하기 위해서 어떤 값의 타입 뒤에 물음표(`?`)를 씁니다.

``` swift
var optionalString: String? = "Hello"
print(optionalString == nil)

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
```

> 실험(EXPERIMENT):
<!-- Change `optionalName` to `nil`. What greeting do you get? Add an `else` clause that sets a different greeting if `optionalName` is `nil`. -->
> `optionalName`의 값을 `nil`로 바꿔 봅시다. 여러분은 어떤 인사말(greeting)을 얻을 수 있습니까? 만약 `optionalName`이 `nil`이라면 다른 인사말을 설정하는 `else` 절을 추가해봅시다.

<!-- If the optional value is `nil`, the conditional is `false` and the code in braces is skipped. -->
만약 옵션널한(optional) 값이 `nil`이라면, 그 조건문은 `false`(즉 거짓)이 되고 중괄호 안에 있는 코드를 건너뛰게 됩니다.
Otherwise, the optional value is unwrapped and assigned to the constant after `let`, which makes the unwrapped value available inside the block of code.
다른 방법으로, 옵션널한 값이 풀어져 `let` 뒤에 상수로 할당되면, 풀어진 값은 코드의 블록 안에서 유용하게 된다.

---
<!-- Another way to handle optional values is to provide a default value using the `??` operator. -->
옵션널한(optional) 값들을 다루는 다른 방법은 `??`라는 연산자를 사용하여 디폴트(default) 값을 제공하는 것이다.
<!-- If the optional value is missing, the default value is used instead.-->
옵션널(optional) 값이 빠져있다면, 대신 이 디폴트(default) 값을 사용할 것이다.

``` swift
let nickName: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickName ?? fullName)"
```

<!-- Switches support any kind of data and a wide variety of comparison operations—they aren’t limited to integers and tests for equality. -->
switch문은 어떤 종류의 자료와 광범위하게 다양한 비교 연자들을 지원합니다 - 즉 '동등성을 위한(for equality)' 시험과 정수들에 제한이 없습니다.

``` swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
```
> 실험(EXPERIMENT):
<!-- > Try removing the `default` case. What error do you get? -->
> (위에서) `default` 부분를 지워보자. 여러분에게 어떤 에러가 발생하는가?

<!-- Notice how `let` can be used in a pattern to assign the value that matched that part of a pattern to a constant. -->
`let`으로 어떤 상수에서 그 패턴의 부분이 매칭되는 값을 구병하는 상수의 주목하자.

---
<!-- After executing the code inside the switch case that matched, the program exits from the switch statement. -->
매칭한 그 스위치 케이스의 안의 코드를 실행한(executing) 다음, 프로그램은 그 스위치 진술 문장에 존재하게 됩니다.
<!-- Execution doesn’t continue to the next case, so there is no need to explicitly break out of the switch at the end of each case’s code. -->
실행은 그 다음 케이스를 진행하지 않기에, 각 케이스들 코드의 마지막 부분에서 명시적으로 이 스위치 문에서 빠져나가기 위하여 멈출 필요가 없습니다.

---
<!-- You use `for-in` to iterate over items in a dictionary by providing a pair of names to use for each key-value pair. -->
여러분은 `for-in`문을 사용하여 각각 키-값 쌍으로 사용할 수 있는 이름들의 쌍을 제공하여 딕셔너리안에 있는 요소들(items)을 반복 처리할 수 있습니다.
Dictionaries are an unordered collection, so their keys and values are iterated over in an arbitrary order.
딕셔너리들을 '규칙적이지 않은(unordered)' 집단이기에, 그들의 키와 값들은 임의의 규칙으로 반복됩니다.

``` swift
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (kind, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}
print(largest)
```
> 실험(EXPERIMENT):
<!-- Add another variable to keep track of which kind of number was the largest, as well as what that largest number was. -->
> 가장 큰 수였던 어떤 숫자가 가장 큰 수로 저장되는지 확인하기 위해 다른 변수를 추가하고, 가장 큰 수로 저장된 숫자가 무엇인지 확인해보라.

<!-- Use `while` to repeat a block of code until a condition changes. -->
조건이 변경될 때까지 코드의 블럭이 반복되는 `while`문을 사용해보자.
<!-- The condition of a loop can be at the end instead, ensuring that the loop is run at least once. -->
루프(loop)의 조건은, 그 조건이 적어도 한번은 작동하게 보장하기 위해서는, 그 대신에 (번역자 주: 다음과 같이) 끝 부분에 있을 수 있습니다.

``` swift
var n = 2
while n < 100 {
    n = n * 2
}
print(n)

var m = 2
repeat {
    m = m * 2
} while m < 100
print(m)
```

<!-- You can keep an index in a loop by using ..< to make a range of indexes. -->
여러분들은 인텍스들의 범위를 만들기 위하여 `..<`을 사용하여 루프안에서 인텍스를 유지할 수 있습니다.

``` swift
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
```

<!-- Use `..<` to make a range that omits its upper value, and use `...` to make a range that includes both values. -->
가장 마지막 값을 제외하고 범위를 만들기 위해서는 `..<`을 사용하고, 양쪽 끝 두 값 모두를 범위에 포함하게 만들기 위해서는 `...`을 사용하자.

## 함수와 클로저(Functions and Closures)

<!-- Use `func` to declare a function. -->
함수를 선언하기 위하여 `func`를 사용해봅시다.
Call a function by following its name with a list of arguments in parentheses.
괄호안에 함수의 이름과 괄호안에 인자(arguments)들을 넣을 수 있습니다. 함수를 호출할 때
Use `->` to separate the parameter names and types from the function’s return type.
매개변수(parameter) 이름들과 그 함수의 반환 분리해서 `->` 사용해 타입 이름을 표기하면 함수 반환 값의 타입을 지정할 수 있습니다.

``` swift
func greet(person: String, day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")
```

> 실험(EXPERIMENT):
<!-- > Remove the `day` parameter. Add a parameter to include today’s lunch special in the greeting -->
>  `day` 매개변수를  지우자. 위의 인사말에 오늘의 특별한 점심을 포함하도록 매개 변수를 추가하자.

By default, functions use their parameter names as labels for their arguments.
기본적으로(By default), 함수들은 그들의 인자를 위하여 매개 변수 이름을 라벨(labels)로 사용합니다.
Write a custom argument label before the parameter name, or write `_` to use no argument label.

``` swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

Use a tuple to make a compound value—for example, to return multiple values from a function.
튜플(tuple)을 사용하 여러개의 값을 반환할 수 있습니다.
The elements of a tuple can be referred to either by name or by number.

``` swift
func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
    var min = scores[0]
    var max = scores[0]
    var sum = 0

    for score in scores {
        if score > max {
            max = score
        } else if score < min {
            min = score
        }
        sum += score
    }

    return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
print(statistics.2)
```

Functions can also take a variable number of arguments, collecting them into an array.

``` swift
func sumOf(numbers: Int...) -> Int {
    var sum = 0
    for number in numbers {
        sum += number
    }
    return sum
}
sumOf()
sumOf(numbers: 42, 597, 12)
```

> 실험(EXPERIMENT):
<!-- > Write a function that calculates the average of its arguments. -->
>  그 인자들의 평균값을 계산하는 함수를 써보자.

<!-- Functions can be nested. -->
함수는 중첩해서 사용할 수도 있습니다.
Nested functions have access to variables that were declared in the outer function.
중첩(Nested)된 함수는 감싸고 있는 함수에서 선언된 변수에 접근할 수 있습니다.
<!-- You can use nested functions to organize the code in a function that is long or complex. -->
여러분들은 함수 안의 코드가 길거나 복잡해지면 이를 정리하기 위해서 중첩된 함수를 사용할 수 있습니다.

``` swift
func returnFifteen() -> Int {
    var y = 10
    func add() {
        y += 5
    }
    add()
    return y
}
returnFifteen()
```

<!-- Functions are a first-class type. -->
함수는 최상위(first-class) 타입입니다.
<!-- This means that a function can return another function as its value. -->
이는 특정 함수가 다른 함수를 자신의 값(value)으로 반환할 수 있다는 것을 의미합니다.

``` swift
func makeIncrementer() -> ((Int) -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
var increment = makeIncrementer()
increment(7)
```

A function can take another function as one of its arguments.
특정 함수는 다른 함수를 자신의 인자(arguments)중의 하나로 받을 수 있습니다.

``` swift
func hasAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
    for item in list {
        if condition(item) {
            return true
        }
    }
    return false
}
func lessThanTen(number: Int) -> Bool {
    return number < 10
}
var numbers = [20, 19, 7, 12]
hasAnyMatches(list: numbers, condition: lessThanTen)
```

Functions are actually a special case of closures: blocks of code that can be called later.
함수란 실제로 클로저(closures)의 특별한 케이스입니다: 코드의 블럭(blocks)이라고 후에 부르데 될 것입니다.
The code in a closure has access to things like variables and functions that were available in the scope where the closure was created, even if the closure is in a different scope when it is executed—you saw an example of this already with nested functions.
심지어 코트 안의 클로저가 실행될 때 다른 영역안에 있더라도, 그 코드는 그 클로저가 생성된 영역안에서 유용한 변수들과 함수들 같은 것들에 접근한다-여러분들은 이런 예를 이미 중첩된 함수에서 봤다.
You can write a closure without a name by surrounding code with braces (`{}`).
여러분들은 중괄호(`{}`)로 코드를 둘러싸지 않아도 클로저를 사용할 수 있습니다.
 Use `in` to separate the arguments and return type from the body.
`in`를 사용해서 인자와 반환값 타입을 분리해

``` swift
numbers.map({
    (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

> 실험(EXPERIMENT):
<!-- > Rewrite the closure to return zero for all odd numbers. -->
> 모든 홀수값을 0으로 반환하도록 클로저를 수정해보자.

<!-- You have several options for writing closures more concisely. -->
여러분이 더 간결하게 클로저를 쓰기 위한 몇 가지 선택사항(options)이 있습니다.
<!-- When a closure’s type is already known, such as the callback for a delegate, you can omit the type of its parameters, its return type, or both. -->
델리게이트(delegate)를 위한 콜백(callback)처럼, 이미 클로저의 타입을 알 경우에는, 여러분은 그 클로저의 매개 변수의 타입이나 반환 값 타입, 또는 모두를 생략할 수 있습니다.
<!-- Single statement closures implicitly return the value of their only statement. -->
한 줄짜리 구문(statement)으로 된 클로저는 단지 그 구문의 값만 반환합니다.

``` swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
```

<!-- You can refer to parameters by number instead of by name—this approach is especially useful in very short closures. -->
여러분은 이름을 대신해서 숫자로 매개 변수를 참고할 수 있습니다 — 이런 접근은 매우 짧은 클로저에서 특히 유용합니다.
A closure passed as the last argument to a function can appear immediately after the parentheses.
클로저는 그 괄호 뒤에 즉시 나올 수 있는 함수의  
<!-- When a closure is the only argument to a function, you can omit the parentheses entirely. -->
클로저는 어떤 함수의 인자일 때, 괄호를 완전히 생략할 수 있습니다.

``` swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
```

## 객체와 클래스(Objects and Classes)

<!-- Use `class` followed by the class’s name to create a class. -->
클래스를 생성하려면 `class`를 사용하고 그 뒤에 그 클래스 이름을 씁니다.
<!-- A property declaration in a class is written the same way as a constant or variable declaration, except that it is in the context of a class. -->
클래스 안의 속성(property)을 선언하는 것은 상수나 변수를 선언하는 것과 같은 방법으로 쓰면됩니다.
<!-- Likewise, method and function declarations are written the same way. -->
게다가(Likewise), 메소드(method)와 함수 선언은 같은 방법을 쓰시면 됩니다.

``` swift
class Shape {
    var numberOfSides = 0
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

> 실험(EXPERIMENT):
<!-- > Add a constant property with `let`, and add another method that takes an argument.
 -->
>  `let`을 가지고 상수 속성을 추가하고, 다른 인자를 갖는 다른 메소드도 추가하세요.

<!-- Create an instance of a class by putting parentheses after the class name.-->
특정 클래스의 인스턴스를 생성하려면 그 클래스 이름 뒤에 괄호를 넣으면 됩니다.
<!-- Use dot syntax to access the properties and methods of the instance. -->
점(dot) 문법을 사용하면 인스턴스의 속성이나 메서드에 접근할 수 있습니다.

``` swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

<!-- This version of the `Shape` class is missing something important: an initializer to set up the class when an instance is created. -->
`Shape` 클래스의 이 상태(version)는 중요한 어떤 것이 빠져있습니다: 인스턴스가 생성될 때 그 클래스를 설정하는 초기자(initializer)가 빠져 있습니다.
<!-- Use `init` to create one. -->
`init`를 사용하여 이를 생성해봅시다.

``` swift
class NamedShape {
    var numberOfSides: Int = 0
    var name: String

    init(name: String) {
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

<!-- Notice how `self` is used to distinguish the `name` property from the `name` argument to the initializer. -->
어떻게 초기자에서 `self`가 `name`속성과 `name`인자를 구별하기 위해 사용되는지 주목합니다.
<!-- The arguments to the initializer are passed like a function call when you create an instance of the class. -->
여러분들이 그 클래스의 인스턴스를 생성할 때 초기자에서 인자는 함수를 부르는 것처럼 전달됩니다.
<!-- Every property needs a value assigned—either in its declaration (as with `numberOfSides`) or in the initializer (as with `name`). -->
모든 속성들은 특정 값이 할당될 필요가 있습니다—(`numberOfSides` 처럼) 그 값을 선언하거나 또는 (`name`처럼) 초기화로 말입니다.

Use `deinit` to create a deinitializer if you need to perform some cleanup before the object is deallocated.
만약 여러분이 객체를 해쳬하기(deallocated)하기 전에 정리 작업을 할 필요가 있다면 `deinit`을 사용하여 디이니셜라이저(deinitializer)를 생성합니다.

<!-- Subclasses include their superclass name after their class name, separated by a colon. -->
하위 클래스들(Subclasses)은 그 클래스들 이름 뒤에, 콜론(즉 ':')으로 분리해 상위 클래스(superclass) 이름을 포함시킵니다.
There is no requirement for classes to subclass any standard root class, so you can include or omit a superclass as needed.
꼭 기본 루트 클래스가 필요한 것은 아니기 때문에 상위 클래스를 포함해도 되고 생략해도 됩니다.

<!-- Methods on a subclass that override the superclass’s implementation are marked with `override`—overriding a method by accident, without `override`, is detected by the compiler as an error. -->
하위 클래스에서 상위 클래스에서 구현된 메서드를 재정의(override)하려면 그 메소를 `override`으로 표시해줘야 합니다—`override`가 없이, 우연히 메소드를 재정의하는 것을 컴파일러는 에러로 찾아 냅니다.
<!-- The compiler also detects methods with `override` that don’t actually override any method in the superclass. -->
실제로 상위 클래스에서 어떤 메소드도 재정의하지 메소드들도 컴파일러는 `override`를 사용하여 찾아 냅니다.

``` swift
class Square: NamedShape {
    var sideLength: Double

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        numberOfSides = 4
    }

    func area() ->  Double {
        return sideLength * sideLength
    }

    override func simpleDescription() -> String {
        return "A square with sides of length \(sideLength)."
    }
}
let test = Square(sideLength: 5.2, name: "my test square")
test.area()
test.simpleDescription()
```

> 실험(EXPERIMENT):
<!-- > Make another subclass of `NamedShape` called `Circle` that takes a radius and a name as arguments to its initializer. Implement an area() and a simpleDescription() method on the Circle class. -->
> `Circle`이라는 부르는 `NamedShape`의 또 다른 하위 클래스를 만들고 이 클래스는 이니셜 라이저를 통해 radius와 name을 인자로 받는다. Circle 클래스 안에 area, describe 함수를 구현해보자.

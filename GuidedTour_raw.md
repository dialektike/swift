<!-- Tradition suggests that the first program in a new language should print the words “Hello, world!” on the screen. -->
전통적으로 새로운 컴퓨터 연어의 첫 번째 프로그램은 화면에 “Hello, world”라는 두 단어를 인쇄하는 것입니다.
In Swift, this can be done in a single line:
Swift에서는, 이를 코드 단 한 줄로 구현할 수 있습니다:

``` swift
print("Hello, world!")
```

<!-- If you have written code in C or Objective-C, this syntax looks familiar to you—in Swift, this line of code is a complete program. -->
만약 여러분이 C나 Objective-C으로 코드를 작성해본 적이 있다면, 여러분에게 이 문법(syntax)은 친숙하게 보일 겁니다 -  Swift에서, 이 코드 (한) 줄은 완전하 프로그램입니다.
<!-- You don’t need to import a separate library for functionality like input/output or string handling. -->
입/출력 또는 문자열을 다루는 것과 같은 ‘컴퓨터의 모든 기능(functionality)’을 위하여 개별적인(separate) 라이브러리를 임포트(import)할 필요는 없습니다.
<!-- Code written at global scope is used as the entry point for the program, so you don’t need a main() function. -->
전역 범위(Global scope)로 쓰여진 코드는 그 프로그램을 위한  진입점(entry point)로 사용되므로, 여러분은  main() 함수를 사용할 필요가 없습니다.
<!-- You also don’t need to write semicolons at the end of every statement. -->
또한 모든 문장 끝에 세미콜론(즉 ;)을 쓸 필요도 없습니다.

<!-- This tour gives you enough information to start writing code in Swift by showing you how to accomplish a variety of programming tasks. -->
이 견학(tour)은 여러분에게 다양한 ‘프로그램을 짤 과제(programming task)’들을 수행하는 방법을 보여줌으로써 Swift으로 코드 작성을 시작하기 위한 충분한 정보를 제공하고자 합니다.
<!-- Don’t worry if you don’t understand something—everything introduced in this tour is explained in detail in the rest of this book. -->
이해하지 못 하는 것이 있다고 해서 걱정하지 마세요—이 견학에서 소개하는 모든 것들은 이 책의 나머지 부분에서 자세히 설명할 것입니다.

> 주의(NOTE):
<!-- For the best experience, open this chapter as a playground in Xcode. Playgrounds allow you to edit the code listings and see the result immediately. --> 
>가장 좋은 경험을 하기 위해서는, Xcode 안에 있는 Playground으로 이 장을 열어보세요. Playground는 여러분들에게 코드를 수정하는 즉시 그 결과를 볼 수 있게 해줄 것입니다.
> <a href="https://developer.apple.com/library/prerelease/ios/documentation/Swift/Conceptual/Swift_Programming_Language/GuidedTour.playground.zip">Playground 다운 받기</a>

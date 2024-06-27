---
theme: ./
layout: intro
colorSchema: dark
---

<h1 style="font-size: 70px; margin-top: 30px;">
  Kotlin Script 활용하기
</h1>

<h2 style="font-size: 30px; font-weight: bold; position: absolute; bottom: 24px; line-height: 1.2;">
  <span style="color: #8052ff">@kciter</span><br />
  KotlinConf'24<br />
  South Korea
</h2>

<img src="/kotlinconf.png" style="position: absolute; right: 32px; bottom: 16px; width: 500px;" />

---
layout: two-cols
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
colorSchema: dark
---

::left::

# 발표자 소개

- 이선협 (@kciter)
- CoBALT, CTO
- https://realizer.ai
- https://github.com/kciter
- https://kciter.so

::right::

<div style="display: flex; justify-content: center; align-items: center; height: 100%;">
  <img src="avatar.png" style="border-radius: 4px; display: block; margin-top: -100px; width: 280px; height: 280px; box-reflect: below 0px linear-gradient(transparent, rgba(0,0,0,0.1))" />
</div>

---
layout: section
subject: What is Kotlin Script?
---


---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

<Image src="kotlin-gradle-dsl.png" width="700px" />


---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
width: 800
---

# Kotlin을 스크립트 언어처럼!

Kotlin scripting is the technology that enables executing<br />
Kotlin code as scripts without prior compilation or packaging into executables.

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 다른 스크립트 언어처럼 빌드 없이 실행가능!

### Code
```kotlin
// hello.kts
fun main() {
  println("Hello, Kotlin!")
}

main()
```

빌드하거나 패키징할 필요가 전혀 없다!

<spacer gap="20" />

### Shell

```shell
$ kotlinc -script hello.kts
Hello, Kotlin!
```

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 그러나...

<spacer gap="20" />

<div style="position: relative;">
<Image src="experimental.png" width="600" caption="https://kotlinlang.org/docs/custom-script-deps-tutorial.html" />
<span style="font-size: 70px; position: absolute; right: -30px; bottom: -50px; transform: rotate(10deg);">
😱
</span>
</div>

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 써야할 이유가 있나요?

* 베타도 아니고 실험 단계
* 솔직히 써야할 이유는 <accent>전혀 없다!</accent>
* 그럼에도 불구하고 이 발표를 하는 이유?
  * 재밌어 보이니까! ~~<sub>이럴 때 아니면 언제 써보겠습니까</sub>~~

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 일단 어디에 쓸 수 있는지 알아보자!

---
layout: section
subject: Usecase
---

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 크게 봤을 때 사용처는 세 가지

* 빌드를 위한 스크립트
  * 이미 Gradle Kotlin DSL에서 잘 사용되고 있음
* <accent>CLI 환경에서 스크립트 실행</accent>
* <accent>Kotlin 프로그램 런타임에서 스크립트 실행</accent>

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# CLI 환경에서 사용하기

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# Bash Script 대체

Bash Script 대신 Kotlin Script를 사용할 수 있다.

* **Kotlin Script가 가지는 이점은?**
  * Bash Script 보다는 쉬움
  * Type 안정성
  * 외부 라이브러리 사용 가능
* **다른 스크립트 언어로도 가능하지만 Kotlin을 사용하면 더 좋은점?**
  * Kotlin 언어만 익숙한 경우에도 사용 가능
  * Java 생태계와의 호환성
* 솔직히 <danger>성능은 살짝 애매</danger>하다
  * 많은 연산 처리는 빠르겠지만 JVM 워밍업 시간이 필요하므로<br />워밍업 시간이 0에 가까운 Python이나 Node.js에 비해 느릴 수 있다.

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 사용 방법

### SDKMAN으로 `kotlin` 설치
```shell
# Install sdkman
$ curl -s https://get.sdkman.io | bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"

# Install kotlin
$ sdk install kotlin
```

<spacer gap="20" />

### Kotlin Script 작성
```kotlin
// hello.kts
println("Hello, Kotlin!")
```

<spacer gap="20" />

### Kotlin Script 실행
```shell
# Run script
$ kotlinc -script hello.kts
Hello, Kotlin!
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# shebang 사용

### Code
```kotlin
#!/usr/bin/env kotlinc -script

println("Hello, Kotlin!")
```

<spacer gap="20" />

### Shell
```shell
$ chmod +x hello.kts
$ ./hello.kts
Hello, Kotlin!
```

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 성능 비교

이미지 삽입 예정

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# KScript

https://github.com/kscripting/kscript

* `kotlinc`는 기본 기능만 있기 때문에 다른 언어를 대체하기는 역부족
* `kscript`는 `kotlinc`를 래핑하여 다양한 기능을 추가로 제공
  * 스크립트 캐싱
  * 의존성 관리
  * 지원 라이브러리 제공
  * 바이너리 패키징

<spacer gap="20" />

### 설치
```shell
# Install kscript using sdkman
$ sdk install kscript
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 외부 라이브러리 사용하기

### Code
```kotlin {2,4}
// main.kts
@file:DependsOn("com.github.kittinunf.fuel:fuel:2.3.1")

import com.github.kittinunf.fuel.httpGet

val (request, response, result) = 
  "https://httpbin.org/get"
    .httpGet()
    .responseString()
println(result.get())
```

<spacer gap="20" />

### Shell
```shell {2}
$ kscript main.kts
[kscript] Resolving com.github.kittinunf.fuel:fuel:2.3.1...
{
  "args": {},
  "headers": {
    "Accept": "text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2",
    "Host": "httpbin.org",
...
```
---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 바이너리 패키징

Gradle이 필요하며 바이너리는 Java가 설치된 환경에서만 실행 가능

### Shell
```shell
$ kscript --package main.kts # Need Gradle
[kscript] Packaging script 'main' into standalone executable...
[kscript] Packaged script 'main' available at path:
[kscript] /Users/kciter/Library/Caches/kscript/package_07f1f85044b41284dee18d4f8c159650/build/libs/main
$ /Users/kciter/Library/Caches/kscript/package_07f1f85044b41284dee18d4f8c159650/build/libs
$ ./main # Need Java
{
  "args": {},
  "headers": {
    "Accept": "text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2",
    "Host": "httpbin.org",
    "User-Agent": "Java/17.0.3",
    "X-Amzn-Trace-Id": "Root=1-6676a491-5935eb22586d7aa550e76b8d"
  },
  "origin": "1.225.3.207",
  "url": "https://httpbin.org/get"
}
```

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 런타임 환경에서 사용하기

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# Java Scripting API (JSR-223)

* 스크립트 코드를 JVM 위에 동작하는 프로그램에서 실행할 수 있게 해준다
* JavaScript나 Groovy를 실행 할 수 있다.
* 물론 <accent>Kotlin Script도 실행 가능!</accent>

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 실험 단계라 그런지 문서가 빈약...

Example 저장소가 그나마 유용하다

https://kotlinlang.org/docs/custom-script-deps-tutorial.html

https://github.com/Kotlin/kotlin-script-examples

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# Embedded Host

WIP

---
layout: section
subject: Toy Project
---

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 실제 제품에 반영 할 수는 없지만...

* 뭔가 재밌는 걸 해볼 수 없을까?
* 조건을 만족하는 프로젝트
  * 너무 오래 걸리지 않는
  * Kotlin Script를 사용해야 하는 이유가 있는
  * 그래도 나름 임팩트가 있는
* 그런게 있긴 할까?

<div style="font-size: 100px; position: absolute; right: 50px; bottom: 10px;">
  🤔
</div>

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 그런건 없을 줄 알았지만 있었습니다

<Image src="ruby-warrior.webp" width="400" style="margin-top: 20px;" />

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# Ruby Warrior

* Ruby를 이용하여 퍼즐을 푸는 게임
* 적절한 스크립트를 작성하여 문제를 해결할 수 있다.
* WarriorJS, Python Warrior 등 파생 프로젝튿로 존재
* 스크립트를 즉시 실행할 수 있는 `eval` 기능이 필요하기에 컴파일 언어로는 만들어진 것이 거의 없음
* <accent>Kotlin Script로 만들어보자!</accent>


---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# WIP

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# 좀 더 실용적인건 없을까?

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# Template Engine

WIP

* Kotlin은 이미 HTML DSL을 제공하고 있음
* 이를 활용하여 Template Engine을 만들어보자

---
layout: section
subject: Conclusion
---

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: logo.svg
---

# WIP

---
layout: center
---

<Image src="thankyou.png" width="600" />
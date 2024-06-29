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
headerLogo: /logo.svg
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
  <img src="/avatar.png" style="border-radius: 4px; display: block; margin-top: -100px; width: 280px; height: 280px; box-reflect: below 0px linear-gradient(transparent, rgba(0,0,0,0.1))" />
</div>

<!--
안녕하세요. 이선협입니다.
저는 주식회사 코발트에서 CTO로 재직 중인 올해로 11년차인 개발자입니다.
Realizer라는 원트랙 고객 관계 관리 서비스를 재작, 운영하고 있습니다.
평소 취미로 블로그 아티클을 작성하거나 오픈 소스 코드를 작성하고 있습니다.
만약 저에 대해 더 궁금하시다면 슬라이드 링크를 참조해주세요.
-->

---
layout: section
subject: What is Kotlin Script?
---

<!--
먼저 이 발표의 주제인 코틀린 스크립트가 무엇인지 알아보겠습니다.
코틀린 스크립트라는 것 자체를 처음 들어보신 분도 있을 것이고 평소에 쓰지는 않더라도 들어는 보신 분들도 있을겁니다.
그래도 여기 오신 분들은 대부분 코틀린으로 무언가를 만들어보신 분들일 텐데요, 그렇다면 높은 확률로 한 번씩은 써보셨을 겁니다.
-->

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

<Image src="/kotlin-gradle-dsl.png" width="700px" />

<!--
화면에 보이는 것은 그라들 코틀린 DSL로 작성한 빌드 스크립트입니다. 평소 관심이 없다면 눈치채지 못했을 수 있는데요, 확장자가 kts입니다.
이 빌드 스크립트를 작성할 때 코틀린 스크립트를 사용합니다. 어떻게보면 우리가 항상 사용하는게 코틀린 스크립트입니다.
-->

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
width: 800
---

# Kotlin을 스크립트 언어처럼!

Kotlin scripting is the technology that enables executing<br />
Kotlin code as scripts without prior compilation or packaging into executables.

<!--
공식 홈페이지에선 코틀린 스크립트를 별도의 컴파일이나 패키징 없이 스크립트처럼 실행할 수 있는 기술이라고 설명하고 있습니다. 딱 이름 그대로죠.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 다른 스크립트 언어처럼 빌드 없이 실행가능!

### Code
```kotlin
// hello.kts
fun say() {
  println("Hello, Kotlin!")
}

say()
```

빌드하거나 패키징할 필요가 전혀 없다!

<spacer gap="20" />

### Shell

```shell
$ kotlinc -script hello.kts
Hello, Kotlin!
```

<!--
그 말처럼 다른 언어 파이썬이나 자바스크립트 같은 스크립트언어와 같이 바로 실행할 수 있습니다.
빌드할 필요도 없고 메인 함수도 없이 바로 실행이 가능합니다.
-->

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 그러나...

<spacer gap="20" />

<div style="position: relative;">
<Image src="/experimental.png" width="600" caption="https://kotlinlang.org/docs/custom-script-deps-tutorial.html" />
<span style="font-size: 70px; position: absolute; right: -30px; bottom: -50px; transform: rotate(10deg);">
😱
</span>
</div>

<!--
하지만 안타까운 점은 이 기술이 아직 실험 단계라는 점입니다. 분명 코틀린 스크립트 자체는 6~7년 정도된 기술이고 빌드 스크립트로 널리 사용되고 있음에도 불구하고 발전이 없습니다. 젯브레인에선 팀시티 같은 자사 제품에 살짝 씩 끼워넣는 것 같기는 한데 아직 크게 관심이 있는 것 같진 않습니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 써야할 이유가 있나요?

* 베타도 아니고 실험 단계
* 현재 JVM 환경에서만 가능
* <accent>솔직히 대안이 많다</accent>
* 그럼에도 불구하고 이 발표를 하는 이유?
  * 재밌어 보이니까! ~~<sub>이럴 때 아니면 언제 써보겠습니까</sub>~~
  * 그래도 없어질 것 같지는 않다

<!--
아직 베타도 아닌 실험 단계인 이 기술을 써야할 이유가 있을까요? 솔직히 말하면 이걸 써야할만한 이유는 딱히 없습니다. 다른 대안이 넘치고 제품의 핵심이 될만한 기술은 아니기 때문에 발전의 여지도 불분명합니다.
그럼에도 불구하고 제가 이 발표를 하는 이유는 재밌어보였기 때문입니다. 일단 코틀린을 스크립트 언어로 쓴다는 것 자체도 재밌는 발상이었고 실험 단계라고는 하지만 이미 빌드 용 기술로 아주 잘 쓰이고 있으니 절대 사라질 것 같지는 않다는 점도 한 몫했습니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 일단 어디에 쓸 수 있는지 알아보자!

* 사용 사례는 총 세 가지
  * 빌드를 위한 스크립트
    * 이미 Gradle Kotlin DSL에서 잘 사용되고 있음
  * <accent>CLI 환경에서 스크립트 실행</accent>
  * <accent>Kotlin 프로그램 런타임에서 스크립트 실행</accent>

<!--
그럼 일단 어디에 쓰일 수 있을지부터 알아봐야겠죠.
당연하게도 먼저 빌드를 위한 스크립트로서 사용할 수 있습니다. 이건 이미 우리 모두 알고 있는 사실이니 제외하도록 하겠습니다.

다른 두 사례는 CLI 환경에서 사용하는 스크립트와 코틀린 런타임에서 스크립트 실행입니다. 오늘 발표에선 이 두 사례에서 무엇을 할 수 있을지를 살펴볼 예정입니다
-->

---
layout: section
subject: Alternative shell-scripting
---

<!--
그럼 CLI 환경에서 무엇을 할 수 있을지 살펴볼까요? 먼저 당연히 쉘 스크립트를 대체할 수 있습니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Shell Script 대체

Shell Script 대신 Kotlin Script를 사용할 수 있다.

* **Kotlin Script가 가지는 이점은?**
  * Shell Script 보다는 쉬움
  * Type 안정성
  * 외부 라이브러리 사용 가능
* **다른 스크립트 언어로도 가능하지만 Kotlin을 사용하면 더 좋은점?**
  * Kotlin 언어만 익숙한 경우에도 사용 가능
  * JVM 생태계와의 호환성
* 솔직히 <danger>성능은 살짝 애매</danger>하다
  * 많은 연산 처리는 빠르겠지만 JVM 워밍업 시간이 필요하므로<br />워밍업 시간이 0에 가까운 Python이나 Node.js에 비해 느릴 수 있다.

<!--
구체적으론 쉘 스크립트를 대체하는 것이 가능합니다.
코틀린 스크립트가 쉘 스크립트에 비해 가질 수 있는 이점은 뭐가 있을까요?
일단 당연히 쉘 스크립트보다는 쉽습니다. 쉘 스크립트는 특유의 외우기 어려운 문법, 코드 골프로 인한 가독성 문제로 간단한 스크립트를 짜는 것도 쉽지 않습니다.

그리고 타입 안정성 측면에서도 우위에 있습니다. 빌드 시간이 있는 것은 아니지만 Intellij 같은 툴에서 타입 체크를 해주기 때문에 실행 전에 미리 확인하는 것이 가능합니다.

마지막으로 외부 라이브러리 사용이 가능합니다. 풍부한 JVM 생태계의 도움을 받을 수 있다는 뜻입니다.

물론 이런건 코틀린 스크립트가 아닌 다른 스크립트 언어에서도 가능한 일입니다. 이런 경우 코틀린 스크립트가 가져갈 수 잇는 이점은 코틀린 언어에 더 익숙하거나 JVM 생태계 정도 밖에 이점을 말할 수가 없습니다.

성능도 좀 애매합니다. 많은 연산 처리를 할 때는 타 스크립트 언어보다 빠르겠지만 JVM 워밍업 시간이 존재해서 실행 즉시 바료 처리하는 파이썬이나 노드에 비해 느립니다. 쉘에선 대부분 짧은 연산을 처리한다는 점을 생각하면 치명적인 단점입니다.
-->

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Kotlin을 사용하는 조직에선 쓸만할지도?

조직 내부에서 사용하는 툴을 만들 때 쓰면 어떨까?

<!--
그렇지만 어차피 로컬에서 돌리는 스크립트라면 그 약간의 시간 차이가 크게 중요하지도 않습니다. 만약 코틀린을 사용하는 조직이라면 다양한 언어로 툴을 만드는 것보다 언어를 통일하는게 비용이나 유지보수 측면에서 더 좋습니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
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

<!--
여러 사용 사례를 다루기 전에 간단하게 사용 방법을 살펴보겠습니다.

화면을 보시다시피 그다지 어렵지 않습니다. sdkman이라는 의존성 관리 툴을 이용하여 코틀린을 설치할 수 있습니다. 여기서 코틀린을 설치하면 kotlinc라는 것을 통해 코틀린 스크립트를 실행하는 것이 가능합니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
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

<!--
shebang을 사용하면 명령어를 생략하고 실행하는 것도 가능합니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# KScript

https://github.com/kscripting/kscript

* `kotlinc`는 기본 기능만 있기 때문에 다른 언어를 대체하기는 역부족
* `kscript`는 `kotlinc`에 비해 다양한 기능을 추가로 제공
  * 스크립트 캐싱
  * 의존성 관리
  * 바이너리 패키징

<spacer gap="20" />

### 설치
```shell
# Install kscript using sdkman
$ sdk install kscript
```

<!--
그런데 공식적으로 제공하는 kotlinc는 사용하기엔 너무 적은 기능만 제공하기 때문에 애매합니다. 그래서 보통 오픈소스로 제공하는 kscript라는 것을 많이 사용합니다.

여러 추가 기능이 있지만 kscript는 핵심적인 세 가지 기능을 제공합니다. 먼저 스크립트 캐싱을 통해 두 번째 실행할 때는 실행 시간을 단축시켜 줍니다.

그리고 의존성을 관리해줍니다. 스크립트 내에 필요한 의존성을 적어두면 알아서 설치하고 실행합니다.

마지막으로 바이너리로 패키징해주는 기능이 있습니다. 패키징하면 코틀린 없이 java만 설치되어 있어도 실행이 가능합니다.

주의할 점으로 아직 코틀린 2.0에선 실행이 안됩니다. 그래서 1.9 버전대를 사용해야 합니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
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

<!--
여기서 스크립트 작성할 때 가장 많이 와닿는 건 역시 외부 라이브러리 사용인데요,
슬라이드 화면 예시를 보시면 DependsOn을 통해 의존성을 설정할 수 있고 그 후에 스크립트를 실행하면 알아서 설치하는 것을 볼 수 있습니다.

노드의 package.json이나 파이썬의 requirements.txt 처럼 외부로 빼지 않고 스크립트 내부에 기술한다는 점이 좀 색다르긴 합니다.
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
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

<!--
그리고 바이너리 패키징도 재밌습니다. 그냥 단순히 명령어 하나만 입력해주면 알아서 바이너리로 만들어줍니다. 바이너리로 만들고나면 다른거 필요없이 자바 실행 환경만 갖추면 되기 때문에 만약 내가 내부 툴을 조직에 배포하고 싶다면 거쳐야할 허들이 줄어든다고 볼 수 있습니다.
15분
-->

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# IntelliJ와 함께 사용하기

`kscript --idea`를 사용하면 자동으로 IntelliJ에서 편집할 수 있게 구성해준다.

<Image src="/autocomplete.png" />

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# args 사용

kscript를 이용하면 자동으로 args를 받아올 수 있다

### Code
```kotlin
println(args.joinToString(", "))
```

<spacer gap="30" />

### Shell
```bash
$ kotlinc --script args.kts hi hello bye

$ kscript args.kts hi hello bye
hi, hello, bye
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 여러 라이브러리와 함께 사용해보자

* Clikt : https://github.com/ajalt/clikt
* Mordant : https://github.com/ajalt/mordant


---
layout: two-cols
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Clikt

CLI 입력을 쉽게 처리할 수 있다

::left::

```kotlin
// ...

class Hello : CliktCommand() {
  val count: Int by option(help="Number of greetings").int().default(1)
  val name: String by option(help="The person to greet").prompt("Your name")

  override fun run() {
    repeat(count) {
      echo("Hello $name!")
    }
  }
}

Hello().main(args)
```

::right::

```bash
$ kscript clikt.kts --count 3       
Your name: kciter
Hello kciter!
Hello kciter!
Hello kciter!
```


---
layout: two-cols
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Mordant

Terminal UI를 그릴 수 있게 도와준다

::left::

```kotlin
val table = table {
  tableBorders = NONE
  borderType = SQUARE_DOUBLE_SECTION_SEPARATOR
  align = RIGHT
  column(0) {
    align = LEFT
    style = magenta
  }
  column(3) {
    style = magenta
  }
  header {
    style = magenta
    row("", "Projected Cost", "Actual Cost", "Difference")
  }
  ...
```

::right::

```bash
$ kscript ./table.kts 

          │ Projected Cost │ Actual Cost │ Difference 
══════════╪════════════════╧═════════════╪════════════
 Food     │           $400          $200 │       $200 
──────────┼──────────────────────────────┼────────────
 Data     │           $100          $150 │       $-50 
──────────┼──────────────────────────────┼────────────
 Rent     │           $800          $800 │         $0 
──────────┼──────────────────────────────┼────────────
 Candles  │             $0        $3,600 │    $-3,600 
──────────┼──────────────────────────────┼────────────
 Utility  │           $154          $150 │        $-5 
══════════╪══════════════════════════════╧════════════
 Subtotal │                                  $-3,455  
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 해볼 수 있는건 많다!

* 배포 자동화
* 온보딩 툴
* 데이터 전처리
* 시드 데이터 추가
* ...

더 많은 예제는 https://github.com/kciter/kotlin-script-examples

---
layout: section
subject: Embedded Scripting
---

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Runtime에 Kotlin Script를 실행하는 두 가지 방법

* Java Scripting API (JSR-223)
* Embeddable Host

---
layout: center
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 실험 단계라 그런지 문서가 빈약...

Example 저장소가 그나마 유용하다

https://kotlinlang.org/docs/custom-script-deps-tutorial.html

https://github.com/Kotlin/kotlin-script-examples


---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Java Scripting API (JSR-223)

* 스크립트 코드를 JVM 위에 동작하는 프로그램에서 실행할 수 있게 해준다
* JavaScript나 Groovy를 실행 할 수 있다.
* 물론 <accent>Kotlin Script도 실행 가능!</accent>

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Java Scripting API (JSR-223)

* `org.jetbrains.kotlin:kotlin-scripting-jsr223` 의존성 필수
  * 라이브러리 이용이나 다른 스크립트 불러오기는 직접 구현해야함
* `kotlin-main-kts`를 사용하는 경우 extension을 `main.kts`로 지정하면 알아서 다 해준다
  * `org.jetbrains.kotlin:kotlin-main-kts` 추가 필요
  * 의존성 관리, 다른 스크립트 불러오기 등 필요한 것들을 미리 다 구현해둠

***

```kotlin
import javax.script.ScriptEngineManager

fun main() {
  val engine = ScriptEngineManager().getEngineByExtension("main.kts")!!
  engine.eval(
    """
      val a = 2
      val b = 3
      println("a + b = ${'$'}{a + b}")
    """.trimIndent() // Output: a + b = 5
  )
}
```


---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Java Scripting API (JSR-223)

스크립트 시작 전 미리 값을 넣어두는 것도 가능하다.

```kotlin {5,6,9}
import javax.script.ScriptEngineManager

fun main() {
  val engine = ScriptEngineManager().getEngineByExtension("main.kts")!!
  engine.put("a", 2)
  engine.put("b", 3)
  engine.eval(
    """
      println("a + b = ${'$'}{a + b}")
    """.trimIndent()
  )
}
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Embeddable Host

* 내장형 컴파일러를 사용하는 방식
* `kotlin-scripting-jsr223`도 내부적으로 사용하고 있다.
  * 분리한 이유는 훗날 멀티플랫폼에서 사용하기 위함이 아닐까 추측 중 (자료가 너무 없다..)
* Script Definition과 Scripting Host를 만들어야 한다
* 공식 홈페이지는 이 방식만 설명하고 있다
  * https://kotlinlang.org/docs/custom-script-deps-tutorial.html
* 코드가 너무 길어지므로 여기선 생략

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 뭘 할 수 있을까?

* 실험 단계기 때문에 실제 제품에 반영하는건 절대 안됨
  * 어떤 문제가 있을지 알 수 없다
* 그래도 뭔가 해볼 수 없을까?

<div style="font-size: 100px; position: absolute; right: 50px; bottom: 10px;">
  🤔
</div>

---
layout: two-cols
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# HTML Template

* `kotlinx.html`을 이용하여 HTML을 Kotlin DSL로 작성 가능
* 스크립트 파일을 외부로 뺀다면 컴파일 타임 없이 템플릿 작성 가능

::left::
```kotlin
import javax.script.ScriptEngineManager

data class Params(val name: String)

fun main() {
  val engine = ScriptEngineManager().getEngineByExtension("main.kts")!!
  engine.put("params", Params("Kotlin"))
  engine.eval("""
    @file:DependsOn("org.jetbrains.kotlinx:kotlinx-html-jvm:0.8.0")
    import kotlinx.html.*; import kotlinx.html.stream.*; import kotlinx.html.attributes.*
    
    print(createHTML().html {
        body {
            h1 { +"Hello, ${"$"}{params.name}!" }
        }
    })""".trimIndent()
  )
}
```

::right::

```
<html>
  <body>
    <h1>Hello, Kotlin!</h1>
  </body>
</html>
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 코딩 테스트

* 사용자가 작성한 코드를 실행, 채점

```kotlin
import javax.script.ScriptEngineManager

fun main() {
  val engine = ScriptEngineManager().getEngineByExtension("main.kts")!!
  val solutionCode = "fun solution(a: Int, b: Int) = a + b"
  engine.put("args", arrayOf(1, 5))
  engine.put("answer", 6)
  engine.eval("""
    $solutionCode
    println(solution(args[0] as Int, args[1] as Int) == answer)
  """.trimIndent()
  )
}
```

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# Toy Project: Ruby Warrior

* Ruby를 이용하여 퍼즐을 푸는 게임
* 적절한 스크립트를 작성하여 문제를 해결할 수 있다.
* WarriorJS, Python Warrior 등 파생 프로젝트로 존재
* 사용자가 입력한 코드를 실행할 수 있어야함

<Image src="/ruby-warrior.webp" width="300" style="margin-top: 20px;" />

---
layout: section
subject: Conclusion
---

---
layout: default
headerEnable: true
headerTitle: Kotlin Script 활용하기
headerLogo: /logo.svg
---

# 실험 단계지만 쓰려면 잘 쓸 수 있을 것 같다!

* 다른 스크립트 언어를 대체할 수 있는가?
  * 아직 많이 부족하다
  * 팀 내부에서 협의하고 쓰는건 괜찮을지도?
    * 팀이 코틀린을 주력으로 사용한다면..
    * ex) Spring 서버팀, Android 팀 등
* 그렇지만 Embedded Scripting은 아직 쓰기엔 많이 애매하다
  * Stable 단계가 아니라는 점이 가장 크다
  * Usecase가 애매하다
    * 빌드 타임을 줄이는 용도로 UI나 설정 등에는 쓸 수 있을지도?
    * 게임 개발에서 Lua 같은 사례


---
layout: center
---

<Image src="/thankyou.png" width="600" />

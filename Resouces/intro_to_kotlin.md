# Kotlin Quick Reference
This reference summarizes the topics covered in the Kotlin Bootcamp course in the form of code
snippets. See the<a href="https://kotlinlang.org/docs/reference/">Kotlin Language Documentation</a> for full reference. See the <a href="https://try.kotlinlang.org/#/Examples/Hello,%20world!/Simplest%20version/Simplest%20version.kt">Kotlin Koans</a> for more
snippets to practice with. See the Kotlin Bootcamp course if you need anything explained.

You can also check this <a href="https://www.youtube.com/playlist?list=PLrnPJCHvNZuAIbejjZA1kGfLeA8ZpICB2">YouTube playlist</a> for your reference.

If you are a Java developer who wants to learn Kotlin and enhance your career prospects, then this is the <a href="https://www.udemy.com/course/kotlin-for-java-developers/">perfect course</a> for you. It allows you to use your Java skills to learn Kotlin faster.
***
<a href="#lesson0"><h3>Lesson 0</h3></a>

<a href="#lesson1"><h3>Lesson 1</h3></a>

* <a href="#helloKotlin">Hello Kotlin Function</a>
* <a href="#helloKotlin">Hello Kotlin Program</a>
* <a href="#operators">Operators</a>
* <a href="#operators">Type conversion</a>
* <a href="#numberFormatting">Number Formattion</a>
* <a href="#numberFormatting">var (immutable)& var (mutable)</a>
* <a href="#nullablity">Nullablity </a>
* <a href="#nullablity">String / String Templates</a>
* <a href="#ifelse">if/else</a>
* <a href="#ifelse">When</a>
* <a href="#listof">listOf / mutableListOf</a>
* <a href="#listof">arrayOf / mutableArrayOf / intArray...</a>
* <a href="#forloop">for loop</a>
* <a href="#forloop">for (elements in swarm) {...}</a>

<a href="#lesson2"><h3>Lesson 2</h3></a>

* <a href="#functions">Functions</a>
* <a href="#functions">Compact Functions</a>
* <a href="#filters">Filters</a>
* <a href="#filters">Lambas (anonymous functions)</a>
* <a href="#higherOrder">Higher order functions (fun with fun args)</a>

<a href="#lesson3"><h3>Lesson 3</h3></a>

* <a href="#class">Class</a>
* <a href="#class">Visiblity</a>
* <a href="#inheritance">Inheritance</a>
* <a href="#inheritance">Abstract Classes</a>
* <a href="#interfaces">Interfaces</a>
* <a href="#dataClasses">Data Classes</a>
* <a href="#interfaces">Composition </a>
* <a href="#dataClasses">Singleton / object</a>
* <a href="#enum">enum</a>

<a href="#lesson4"><h3>Lesson 4</h4></a>

* <a href="#pairs">Pairs</a>
* <a href="#pairs">Lists</a>
* <a href="#mapping">Mapping</a>
* <a href="#mapping">Constants</a>
* <a href="#extensionfunctions">Extension functions</a>
* <a href="#extensionfunctions">Property extensions</a>
* <a href="#genericlasses">Generic classes </a>
* <a href="#genericlasses">Generics: Full example</a>
* <a href="#genericconstraint">Generic constraint</a>
* <a href="#genericconstraint">In and Out types</a>
* <a href="#genericmethods">Generic functions and methods </a>
* <a href="#genericmethods">Inline/ reified</a>
* <a href="#anno">Annotations</a>
* <a href="#anno">Reflection </a>
* <a href="#annogetset">Annotations for getters & setters</a>
* <a href="#annogetset">Labeled breaks</a>

<a href="#lesson5"><h3>Lesson 5</h3></a>

* <a href="#lambdarecap">Lambda recap</a>
* <a href="#lambdarecap">Higher order function</a>
* <a href="#standardLibrary">Standard Libary: Apply & Run</a>
* <a href="#standardLibrary"> Standard Libary: With & Repeat</a>
* <a href="#inline">Inline</a>
* <a href="#inline">Lambda instead ofSAM</a>

<a href="https://github.com/smartherd/KotlinTutorial/tree/master/src"><h3><i>More Resources</i></h3></a>

<a id="lesson0"></a>
### Lesson 0
- [Install JDK](https://www.oracle.com/java/technologies/javase-downloads.html) if you don&#180;t have it.
- [Link to downloading IntelliJ](https://www.jetbrains.com/idea/download/#section=windows)
- Starting the interpreter: <b>Tools>Tools > Kotlin > Kotlin REPL</b>

Or

- You can run your code in <a href="https://play.kotlinlang.org/">Kotlin playground</a>.
Kotlin Playground is an online sandbox to explore Kotlin
programming language. Browse code samples directly in the browser

<a id="lesson1"></a>
### Lesson 1
| Hello  Kotlin function <a id="helloKotlin"></a> | Hello Kotlin program  |
| :--------------- | :------------ |
|  fun printHello () {<br> println ("Hello Kotlin")<br> }<br> printHello()| fun main (args:  Array&#60;String&#62;) {<br> println("Hello ${args[0]} ")<br>} |

| Operators<a id="operators"></a> | Type conversion  |
| :--------------- | :------------ |
| *, fish.times(6)<br>/, fish.div(10)<br>+, fish.plus(3)<br>-, fish.minus(3)| 1.toLong()<br>1.toString() |

|Number formatting <a id="numberFormatting"></a>| val (immutable) & var (mutable) |
| :--------------- | :------------ |
|  val oneMillion = 1_000_000<br> val socialSecurityNumber = 999_99_9999L| val aquarium = "my aquarium"<br>var fish = 50<br>var snails : Int = 12 |

|Nullability<a id="nullablity"></a> | Strings / String Templates|
| :--------------- | :------------ |
| var rocks: Int = null //Error<br> var marbles: Int? = null<br>fishFoodTreats?.dec()<br><br>var lotsOfFish: List&#60;String?&#62; = listOf(null, null)<br><br>return fishFoodTreats?.dec() ?:0<br>goldfish!!.eat|"hello" + "fish" + "!"<br>"I have $numberOfFish fish"<br>"Print ${ numberOfFish + 5 } fish"<br>"fish" == "fish"<br>val message = "You are ${ if (length &#60; 5) "fried" else "safe" } fish" |

|if / else <a id="ifelse"></a>| When |
| :--------------- | :------------ |
| if (numberOfFish>numberOfPlants) {<br>println("Good ratio!")<br>} else {<br>println("unhealthy ratio")<br>}<br><br>if (fish in 1..100) println(fish)<br>val isHot= if (temprature > 90) true else false |when (numberOfFish) {<br>0 -> println("Empty tank")<br>in  1..50 -> println("Got fish!") <br> else -> println("Perfect!")<br>}|

| listOf / mutableListOf<a id="listof"></a> | arrayOf / mutableArrayOf / intArray... |
| :--------------- | :------------ |
|  val myList = mutableListOf("tuna",,"shark")<br><br> myList.remove("shark") // OK! <br>val swarm = listOf(fish, plants)| val school =arrayOf("tuna","salmon","shark")<br><br>val mix = arrayOf("fish", 2)<br><br>println(Arrays.toString(intArrayOf(2,"foo")))<br><br>val bigSwarm = arrayOf(swarm,arrayOf("dolphin","whale","orka"))<br><br>val array = Array (5) { it * 2 } |

| for loop<a id="forloop"></a> |
| :--------------- |
| <b>for (element in swarm) {...}</b><br><br> for ((index, element) in swarm.withIndex()){<br>println("Fish at $index is$element")}<br><br>for (i in 'b'..'g') print(i)<br><br>for (i in 1..5) print(i)<br><br>for (i in 3..6 step 2) print(i)  //Prints: 35|  |

<a id="lesson2"></a>
### Lesson 2
| Functions<a id="functions"></a>  | Compact Functions |
|:-------------  |:------------- |
| fun randomDay(): String {return "Monday"} <br><br>fun fishFood (hour: Int, day: String = "Tuesday"): String {}<br><br>fun isTooHot(temperature: Int): Boolean = temperature > 30 |fun isTooHot(temperature: Int) =temperature > 30<br><br>fun shouldChangeWater (day: String, temperature: Int = 22, dirty: Int =20): Boolean {return when { isTooHot(temperature)-> true else -> false}}<br><br>fun getDirtySensorReading() = return 20<br><br>fun shouldChangeWater (day: String, temperature: Int = 22, dirty: Int =getDirtySensorReading()) {...}  |

| Filters<a id="filters"></a>  | Lambdas (anonymous functions) |
| ------------- | ------------- |
| println( decorations.filter {it[0] ==&#180;p&#180;})  | { println("Hello") }()<br><br>val waterFilter = { dirty: Int -> dirty/ 2 }<br><br>val waterFilter : (Int) -> Int = {dirty -> dirty / 2 }  |

|Higher order functions (fun with fun arg)<a id="higherOrder"></a>|
| ------------- |
| fun updateDirty(dirty: Int, operation:(Int) -> Int): Int {return operation(dirty)}<br>updateDirty(50, ::increaseDirty) |

<a id="lesson3"></a>
### Lesson 3
| Class<a id="class"></a> | Visibility  |
| :------------ | :------------ |
|  class Aquarium(var length: Int = 100, var width: Int = 20, var height: Int = 40) {<br><br> constructor(numOfFish: Int): this() {<br><br>init {<br> // do stuff<br> }<br><br>val volume: Int get() {return w &#42; h &#42; l / 1000 }<br><br>init {<br>// do stuff with volume<br>} }| <b>package:</b><br>public - default. Everywhere<br><br>private - file<br><br> internal module<br><br> <br><b>class:</b><br>sealed - only subclass in same file<br><br> <br><b>inside class:</b>public - default. Everywhere.<br><br>private - inside class, not subclasses<br><br>protected - inside class and subclasses<br><br>internal - module|

| Inheritance<a id="inheritance"></a> | Abstract classes  |
| :------------ | :------------ |
| open class Aquarium ….. { <br>open var water = volume * 0.9 <br>open var volume<br>}<br><br>class TowerTank (): Aquarium() {<br>override var volume: Int<br>get() = (w &#42; h &#42; l / 1000 &#42; PI).toInt()<br>          set(value) {<br>h = (value &#42; 1000) / (w &#42; l)<br> } } | abstract class AquariumFish {<br>abstract val color: String<br>}<br><br>class Shark: AquariumFish() {<br>override val color = "gray"<br>} <br><br>class Plecostomus: AquariumFish() {<br>override val color = "gold"<br>} |

| Interfaces<a id="interfaces"></a> | Composition  |
| :------------ | :------------ |
| interface FishAction {<br>fun eat() } <br><br>class Shark: AquariumFish(), FishAction { <br>override val color = "gray"<br>override fun eat() {<br>println("hunt and eat fish") <br>} <br>}<br><br>fun feedFish(fish: FishAction) { <br>// make some food then <br>fish.eat() <br>}  | fun main (args: Array&#60;String&#62;) {<br>delegate()<br> }<br><br>fun delegate() {<br>val pleco = Plecostomus()<br>println("Fish has has color ${pleco.color}")<br>pleco.eat()<br>}<br><br>interface FishAction {<br>fun eat()<br>}<br><br>interface FishColor {<br>val color: String<br>}<br><br>object GoldColor : FishColor {<br>override val color = "gold"<br>}<br><br>class PrintingFishAction(val food: String) : FishAction {<br>override fun eat() {<br>println(food)<br>}<br>}<br><br>class Plecostomus (fishColor: FishColor = GoldColor) : FishAction by PrintingFishAction("eat a lot of algae"), FishColor by fishColor |

| Data Classes <a id="dataClasses"></a>| Singleton / object  |
| :------------ | :------------ |
|data class Decorations(val rocks : String, val wood: String, val diver: String){}<br><br>val d = Decorations("crystal", "wood", "diver") val (rock, wood, diver) = d <br><br>dataClassInstance1.equals(dataClassInstance2) val dataClassInstance3.copy(dataClassInstance2)| object Database <br><br> object MobyDickWhale {<br>val author = "Herman Melville"<br>} |

|enum <a id="enum"></a>|
| :------------ |
|enum class Color(val rgb: Int) {<br>RED(0xFF0000), GREEN(0x00FF00), BLUE(0x0000FF);<br>}<br>Color.RED|

<a id="lesson4"></a>
### Lesson 4
| Pairs <a id="pairs"></a>| Lists  |
| :------------ | :------------ |
| val equipment = "fishnet" to "catching fish" <br>println(equipment.first)<br>println(equipment.second)<br><br> val (tool, use) = fishnet <br> val fishnetString = fishnet.toString()<br>println(fishnet.toList())<br><br>Nesting with parentheses:<br>val equip = ("fishnet" to "catching fish") to ("of big size" to "and strong")<br>equipment.first.first | val testList = listOf(11,12,13,14,15,16,17,18,19,20) listOf<Int>(1,2,3,4,5,6,7,8,9,0).revers ed()<br><br>var symptoms = mutableListOf("white spots", "red spots", "not eating", "bloated", "belly up")<br>symptoms.add("white fungus")<br>symptoms.remove("white fungus")<br>symptoms.contains("red")<br>println(symptoms.subList(4, symptoms.size))<br><br>listOf(1, 5, 3).sum()<br>listOf("a", "b", "cc").sumBy { it.length } |

| Mapping <a id="mapping"></a>| Constants  |
| :------------ | :------------ |
|val cures = hashMapOf("white spots" to "Ich", "red sores" to "hole disease")<br><br>println(cures["white spots"])<br><br> cures.getOrDefault("bloating", "sorry, I don't know")<br><br> cures.getOrElse("bloating") {"No cure for this"}<br><br>val inventory = mutableMapOf("fish net" to 1)<br><br>inventory.put("tank scrubber", 3)<br>inventory.remove("fish net") |const val CONSTANT = "top-level constant" // compile time<br><br>object Constants {<br>const val CONSTANT2 = "object constant"<br>}<br><br>class MyClass {<br>companion object {<br>const val CONSTANT3 = "constant in companion"<br>}<br>} |

| Extension functions<a id="extensionfunctions"></a> | Property extensions  |
| :------------ | :------------ |
|fun String.hasSpaces(): Boolean { <br>val found = this.find { it == &#180; &#180; }<br>return found != null<br>}<br><br>fun extensionExample() {<br>“Does it have spaces?”.hasSpaces()<br>}<br><br>⇒ fun String.hasSpaces() = find { it == &#180; &#180; } != null<br><br>fun AquariumPlant.isRed() = color == "red" <br><br>fun AquariumPlant?.pull() {<br>this?.apply {<br>println("removing $this")<br>}<br>} |val AquariumPlant.isGreen: Boolean<br>get() = color == "green"<br><br>fun propertyExample() {<br>val plant = GreenLeafyPlant(30)<br>plant.isGreen // true<br>} |

| Generic classes<a id="genericlasses"></a> | Generics: Full example  |
| :------------ | :------------ |
|class MyList&#60;T&#62; {<br>fun get(pos: Int): T {<br>TODO("implement")<br>}<br>fun addItem(item: T) {}<br>}<br><br>fun workWithMyList() {<br>val intList: MyList&#60;String&#62;<br>val fishList: MyList&#60;Fish&#62;<br>}  |open class WaterSupply(var needsProcessed: Boolean)<br><br>class TapWater : WaterSupply(true) {<br>fun addChemicalCleaners() {<br>needsProcessed = false<br>}<br>}<br><br> class FishStoreWater : WaterSupply(false)<br><br>class LakeWater : WaterSupply(true) {<br>fun filter() {<br>needsProcessed = false<br>}<br>}<br><br>class Aquarium&#60;T&#62;(val waterSupply: T)<br><br>fun genericsExample() {<br>val aquarium = Aquarium(TapWater())aquarium.waterSupply.addChemicalCleanes()<br>} |

| Generic constraint<a id="genericconstraint"></a> | In and Out Types  |
| :------------ | :------------ |
|Non-nullable:<br>class Aquarium&#60;T: Any&#62;(val waterSupply:T)<br><br>class Aquarium&#60;T: WaterSupply&#62;(val waterSupply:T) |class Aquarium&#60;out T: WaterSupply&#62;(val waterSupply: T) { …}<br><br>interface Cleaner&#60;in T: WaterSupply&#62; {<br>fun clean(waterSupply: T)<br>} |

| Generic functions and methods<a id="genericmethods"></a> | Inline / reified  |
| :------------ | :------------ |
|fun &#60;T: WaterSupply&#62; isWaterClean(aquarium: Aquarium T&#62;) {<br>println("aquarium water is clean: ${aquarium.waterSupply.needsProcessed}" )<br>}<br><br>fun genericsFunExample() {<br>val aquarium = Aquarium(TapWater())<br>isWaterClean(aquarium)<br>}<br><br>fun &#60;R: WaterSupply&#62; hasWaterSupplyOfType() = waterSupply is R | inline fun &#60;reified R: WaterSupply&#62; hasWaterSupplyOfType() = waterSupply is R<br> <br>inline fun &#60;reified T: WaterSupply&#62;WaterSupply.isOfType() = this is T<br><br>inline fun &#60;reified R: WaterSupply&#62; Aquarium&#60;*&#62;.hasWaterSupplyOfType() = waterSupply is R | 

| Annotations<a id="anno"></a> |Reflection  |
| :------------ | :------------ |
|&#64;file:JvmName(“InteropFish”)<br>&#64;JvmStatic fun interop()<br><br>annotation class ImAPlant<br>&#64;ImAPlant class Plant{...}<br><br>val plantObject = Plant::class<br>for (a in plantObject.annotations) {<br>println(a.annotationClass.simpleName)<br>}  |val classobj=Plant::class<br>for(m in classobj.declaredMemberFunctions {<br>println(m.name)<br>} |

| Annotations for getters and setters<a id="annogetset"></a> |Labeled breaks  |
| :------------ | :------------ |
|&#64;Target(PROPERTY_GETTER)<br>annotation class OnGet<br>&#64;Target(PROPERTY_SETTER)<br>Annotation class OnSet<br><br>&#64;ImAPlant class Plant {<br>&#64;get:OnGet<br>val isGrowing: Boolean = true<br>&#64;set:OnSet<br>var needsFood: boolean = false<br>} |fun labels() {<br>loop&#64; for (i in 1..100) {<br>for (j in 1..100) {<br>if (i > 10) break&#64;loop<br>}<br>}<br>} |

<a id="lesson5"></a>
### Lesson 5
| Lambda recap<a id="lambdarecap"></a> |Higher order function  |
| :------------ | :------------ |
|myFish.filter {<br>it.name.contains("i")}.joinToString ("") { it.name } |fun myWith(name: String, block: String.() -> Unit) {<br>name.block()<br>} |

| Standard Library: apply & run<a id="standardLibrary"></a> |Standard Library: with & repeat  |
| :------------ | :------------ |
|fish.run {<br>name<br>}<br><br>val fish2 = Fish().apply {<br>name = “sharky”<br>} |with(fish.name) {<br>println(name)<br>}<br><br>repeat(3) {<br>rep -> println(" current repetition: $rep")<br>} |

| Inline<a id="inline"></a> |Lambda instead ofSAM  |
| :------------ | :------------ |
|Inline fun myWith(name: String, operation: String.() -> Unit) {<br>name.operation()<br>} |fun example() {<br>runNow {<br>println(“Passing a lambda as a Runnable”) <br>}|


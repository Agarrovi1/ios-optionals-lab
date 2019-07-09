# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap
```swift
if userName != nil {
print(userName!)
} else {
print("no name")
}
```

- Method two: Optional binding
```swift
if let realUserName = userName {
print(realUserName)
} else {
print("no name")
}
```
- Method three: Nil coalescing
```swift
var realUserName = userName ?? "no name"
print(realUserName)
```

## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`
```swift
for _ in 0...1 {
if let color = backgroundColor {
print(color)
} else {
backgroundColor = "red"
}
}
```

## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?

if let trueWidth = width, let trueHeight = height {
print("Area is \(trueWidth) * \(trueHeight)")
} else {
print("no width or height found")
}
```


## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?

if let realName = name, let realAge = age, let realHeight = height {
print(realName, realAge, realHeight)
} else {
print("no name, age or height input")
}
```


## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"

var fullName: String
if let realMiddle = middleName {
fullName = "\(firstName) \(middleName) \(lastName)"
} else {
fullName = "\(firstName) \(lastName)"
}
print(fullName)
```


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.
```swift
`let myIntString = "35"`

let myIntString: String? = "35"
if let unwrappedIntString = myIntString {
if let integerVersion = Int(unwrappedIntString) {
print(15 + integerVersion)
}
}
```

## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)

var sum: Int = 0

if let test = testCaseTwo {
if let test0 = test.0 {
sum += test0
}
if let test1 = test.1 {
sum += test1
}
if let test2 = test.2 {
sum += test2
}
}
print(sum)
```


## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}

if let realTuple = tuple {
print("(\(realTuple.0), \(realTuple.1))")
}
```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}

if let realInt = myInt {
print(2 * realInt)
} else {
print("Error: myInt is nil")
}
```


## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}

if let realMyDouble = myDouble {
print(doubleTwo * realMyDouble)
} else {
print("Error: myDouble is nil")
}
```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
isTheGreatest ?? false
```


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}

print(myTuple)
var sum = 0
if let realTuple0 = myTuple.0 {
sum += realTuple0
}
if let realTuple1 = myTuple.1 {
sum += realTuple1
}
if let realTuple2 = myTuple.2 {
sum += realTuple2
}
if let realTuple3 = myTuple.3 {
sum += realTuple3
}
print(sum)
```


## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()

if let stone = evolutionaryStone, let mypoke = pokemon {
if stone == "Electric" && mypoke == "Pikachu" || stone == "Grass" && mypoke == "Bulbasaur" || stone == "Fire" && mypoke == "Charmander" || stone == "Water" && mypoke == "Squirtle" {
print("able to evolve")
} else {
print("stone is not able to evolve pokemon")
}
}
```


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}

if let num = numberOfPeople {
if num % 2 == 0 {
print(num)
}
}
```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}

var product: Int = 1

print(someNumbers)

for i in someNumbers.indices {
if let num = someNumbers[i] {
product *= num
}
}
print(product)
```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]

var cityNames: [String] = []
for i in poorlyFormattedCityNames.indices {
if let cities = poorlyFormattedCityNames[i] {
cityNames.append(cities.uppercased())
}
}
print(cityNames)
```


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}

var evenNumbers: [Int] = []

for i in aBunchOfNumbers.indices {
if let numNums = aBunchOfNumbers[i] {
if numNums % 2 == 0 {
evenNumbers.append(numNums)
}
}
}
print(evenNumbers)
```


## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

```swift
var zipCodeInt: [Int] = []
for i in zipCodeStrings.indices {
if let zipNums = Int(zipCodeStrings[i]) {
zipCodeInt.append(zipNums)
}
}
print(zipCodeInt)
```
## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

```swift
var studentFoodColor: [(String, String, String)] = []
for a in studentInfo.indices {
if let _ = studentInfo[a].2 {
} else {
print("\(studentInfo[a].0) does not have a favorite color")
}
if let food = studentInfo[a].1, let color = studentInfo[a].2 {
studentFoodColor.append((studentInfo[a].0, food, color))
} else {
print("\(studentInfo[a].0) does not have a favorite food or color")
}
}
print(studentFoodColor)

```


## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```swift
var nilCount = 0
if let unwrappedColors = possibleColors {
for a in unwrappedColors.indices {
if let unwrappedTuples = unwrappedColors[a] {
if let tuple0 = unwrappedTuples.0, let tuple1 = unwrappedTuples.1, let tuple2 = unwrappedTuples.2 {
let tupleColor = (tuple0, tuple1, tuple2)
print(tupleColor)
} else {
nilCount += 1
}
} else {
nilCount += 1
}
}
}
print(nilCount)
```


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`
```swift
print(number!!!)

if let bind1 = number {
if let bind2 = bind1 {
if let bind3 = bind2 {
print(bind3)
}
}
}
```

## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`

```swift
var vowels = "aeiou"

var concatenateMonkey = ""
for a in monkeyingAround.indices {
if let unwrapped = monkeyingAround[a] {
var vowelCount = 0
for b in unwrapped {
if vowels.contains(b) {
vowelCount += 1
}
}
if vowelCount < 3 {
concatenateMonkey.append(unwrapped)
}
}
}
print(concatenateMonkey)
```


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`

```swift
if let tupleItself = strangeStructure {
if let tuple0 = tupleItself.0 {
print(tuple0)
}
for a in tupleItself.1 {
for b in a {
if let unwrapFromTuple1 = b {
print(unwrapFromTuple1)
}
}
}
for a in tupleItself.2 {
if let arrayInTuple2 = a {
for b in arrayInTuple2 {
print(b)
}
}
}
print(tupleItself.3)
}
```

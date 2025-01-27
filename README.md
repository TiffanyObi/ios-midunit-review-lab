## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

Answer: 
var newString = "Hello,there"

var newString1 = newString.uppercased()
print(newString1)



2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

Answer: 
var inputString = "Hello,there"
var outputString: String = ""
var counter = 2

for char in inputString {
    if char.isLetter && counter % 2 == 0 {
        outputString.append(char.uppercased())
        counter += 1
    } else if char.isLetter && counter % 2 == 1 {
            outputString.append(char.lowercased())
            counter += 1
    } else {
        outputString.append(char)
    }
}
print(outputString)
// print(counter) = this is 12. there are 10 characters in the string and we started at 2. this shows how many times we've looped through the string which made this problem make more sense for me. 


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

Answer:
var newString2 = ""
for char in inputString {
    if char != "e" {
        newString2.append(char)
    }
}
print(newString2)


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

Answer:
var inputArray:[Int] = [1,5,2,4,1,4]

var highestNumber = 0

for num in inputArray {
    if num > highestNumber {
        highestNumber = num
    }
}
print(highestNumber)

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

Answer:
var inputArray:[Int] = [1,5,2,4,1,4]

var orderArray = inputArray.sorted()
print(orderArray[0])


3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

Answer:
var inputArray2 = [1,5,2,4,1,4]
var arraytotalCount = 0
for num in inputArray2 {
    arraytotalCount += num
}
print(arraytotalCount)

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

Answer:
var inputArray3: [Double] = [3,4.5,7.5,2,1]
var sum: Double = 0

for num in inputArray3 {
    (sum += num / Double(inputArray3.count))
}

print(sum)


5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

Answer:
var inputArray4:[Double] = [3,4.5,7.5,2,1]
var givenNumber:Double = 3
var greaterThanGivenNumber:Double = 0

for num in inputArray4 {
    if num > givenNumber {
        greaterThanGivenNumber += num
        }
}
print(greaterThanGivenNumber)

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

Answer:
var inputArray5:[Double] = [3,4.5,7.5,2,1]
var product: Double = 1

for num in inputArray5 {
    product *= num
}
print(product)


7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

Answer:
var inputArray6: [Int] = [3,6,1,9,4,8]
var inputArraySorted = inputArray6.sorted()
var uniqueSortedInputArray:[String] = []
var smallestValue:String = ""
var secondSmallestValue:String = ""

func findSecondSmallestValue (arr: [Int]) -> (String) {
    for index in inputArraySorted {

if uniqueSortedInputArray.contains(String(index)) {
            continue
            } else {
                uniqueSortedInputArray.append(String(index))
            }
        }
            
smallestValue.append(uniqueSortedInputArray[0])
    
secondSmallestValue.append(uniqueSortedInputArray[1])
    
if Int(secondSmallestValue) ?? 1 > Int(smallestValue) ?? 1 {
        
print("\(secondSmallestValue) is the second smallest value in the array!")
    } else {
    print("Something went wrong.")
}
    return secondSmallestValue
}

findSecondSmallestValue(arr: inputArray6)

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

Answer:
var optArray = [nil, "We", "come", nil, "in", "peace"]

var unOptArray:[String] = []

for index in optArray {
    if index != nil {
        unOptArray.append((index ?? ""))
    }
}

print(unOptArray)

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

Answer:
var optString:String? = nil

var unOptArray2:[String] = []

for char in optArray {
    if char != nil {
        unOptArray.append((char ?? ""))
    }
}
print(unOptArray2)

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

Answer:
func sumOfNonNil(array: [Int?]) -> Int {
    guard var sumOfArray:Int = 0  else {
        return Int()
    }
    for index in inputArray7 {
        if index != nil {
            sumOfArray += index ?? 0
            }
        }
    return sumOfArray
}
print(sumOfNonNil(array: inputArray7))

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

Answer:

let nilInts: [Int?]? = nil

func findNotNil(_ : [Int?]?) -> Int {
for char in nilInts ?? [Int?]() {
    guard var notNil: Int = 0 else {
    }
    if char != nil {
        notNil += char ?? 0
    }
}
    return Int()
}
print(findNotNil(nilInts))

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

Answer:
var inputArray8: [Int?] = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var givenNum = 1
var notNilSUM = 0

func notNilSum(_: [Int?] ) -> Int {

for num in inputArray8 {
        
if num != nil && num != givenNum {
       
notNilSUM += num ?? 0
    }
}
    return notNilSUM
}

print(notNilSum(inputArray8))

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`

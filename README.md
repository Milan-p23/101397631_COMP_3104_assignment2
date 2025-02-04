//
//  LabTests.swift
//
//
//  Created by Przemyslaw Pawluk on 2025-01-31.
//


import Foundation

/*
* Replace following < > with your information

<First and Last name as per registration records>
<StudentID>
*/

/*
Note: foo(z) ➞ x means that function foo for the parametr z returns x
Note: return is not the same as print
*/


//---------------------------------------------------------------------
//Question 1 (2 points)
/*
Write a function that returns true if there exists at least one number
 that is larger than or equal to n. Return false for an empty array [].

 Sample usage
existsHigher([5, 3, 15, 22, 4], 10) ➞ true

existsHigher([1, 2, 3, 4, 5], 8) ➞ false

existsHigher([4, 3, 3, 3, 2, 2, 2], 4) ➞ true

existsHigher([], 5) ➞ false
*/

func existsHigher(_ arr: [Int], _ n: Int) -> Bool {
    for number in arr {
        if number >= n {
            return true
        }
    }
    return false
}

print(existsHigher([5, 3, 15, 22, 4], 10))
print(existsHigher([1, 2, 3, 4, 5], 8))
print(existsHigher([4, 3, 3, 3, 2, 2, 2], 4))
print(existsHigher([], 5))


//---------------------------------------------------------------------
//Question 2 (3 points)
/*
An isogram is a word that has no duplicate letters. Create a function that takes a string and returns either true or false depending on whether or not it's an "isogram".

 Sample usage
isIsogram("Algorism") ➞ true

isIsogram("PasSword") ➞ false
// Not case sensitive.

isIsogram("Consecutive") ➞ false
*/
func isIsogram(_ str: String) -> Bool {
    let lowercasedStr = str.lowercased()
    var uniqueLetters = Set<Character>()
    for letter in lowercasedStr {
        if uniqueLetters.contains(letter) {
            return false
        }
        uniqueLetters.insert(letter)
    }
    return true
}


print(isIsogram("Algorism"))
print(isIsogram("PasSword"))
print(isIsogram("Consecutive"))


//---------------------------------------------------------------------
//Question 3 (5 points)
/*
Create a function that counts the number of times a particular letter shows up in the word search.

Sample usage
letterCounter([
  ["D", "E", "Y", "H", "A", "D"],
  ["C", "B", "Z", "Y", "J", "K"],
  ["D", "B", "C", "A", "M", "N"],
  ["F", "G", "G", "R", "S", "R"],
  ["V", "X", "H", "A", "S", "S"]
], "D") ➞ 3

// "D" shows up 3 times: twice in the first row, once in the third row.

letterCounter([
  ["D", "E", "Y", "H", "A", "D"],
  ["C", "B", "Z", "Y", "J", "K"],
  ["D", "B", "C", "A", "M", "N"],
  ["F", "G", "G", "R", "S", "R"],
  ["V", "X", "H", "A", "S", "S"]
], "H") ➞ 2
*/

func letterCounter(_ arr: [[Character]], _ x: Character) -> Int {
    var count = 0
    for row in arr {
        for char in row {
            if char == x {
                count += 1
            }
        }
    }
    return count
}


let grid: [[Character]] = [
    ["D", "E", "Y", "H", "A", "D"],
    ["C", "B", "Z", "Y", "J", "K"],
    ["D", "B", "C", "A", "M", "N"],
    ["F", "G", "G", "R", "S", "R"],
    ["V", "X", "H", "A", "S", "S"]
]

print(letterCounter(grid, "D"))
print(letterCounter(grid, "H"))



//---------------------------------------------------------------------
//Question 4 (5 points)
/*
Write a function that returns a closure, which transforms its input by adding a particular suffix at the end.

Sample usage
let add_ly = add_suffix("ly")

add_ly("hopeless") ➞ "hopelessly"
add_ly("total") ➞ "totally"
*/

func add_suffix(_ suffix: String) -> (String) -> String {
    return { input in
        return input + suffix
    }
}

let add_ly = add_suffix("ly")
print(add_ly("hopeless"))
print(add_ly("total"))



//---------------------------------------------------------------------


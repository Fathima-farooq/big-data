# Code

```bash
nano sam.scala
scala sam.scala
```

```scala
object Main {
	def main(args: Array[String]) {
		//Code
		println("hello")
	}
}
```

Armstrong number

```scala
object ArmstrongNumber {
    def main(args: Array[String])  {

        val input = 153;

        var sum = 0;
        var armstrongNumber = input;

        while (armstrongNumber > 0) {
            var i = armstrongNumber % 10;
            armstrongNumber = armstrongNumber / 10;
            sum += (i * i * i);
        }

        if (sum == input) {
            println("The given number is Armstrong Number");
        } else {
            println("The given number is NOT a Armstrong Number");
        }
    }
}
```

Prime number or not

```scala
object Main {
	def main(args: Array[String]) {
		var limit = 7
        showPrimes(limit)
    }
    
   def showPrimes(limit: Int): Unit = {
        for (index <- 2 to limit) {
            if (isPrime(index)) println(index)
        }
    }

    def isPrime(number: Int): Boolean = {
        for (factor <- 2 until number) {
            if (number % factor == 0) {
                return false
            }
        }
        true
    }
}
```

Fibonacci series:
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144.
```scala
object Main {
	def main(args: Array[String]) {
		//Code
		var n = 10
		if(n <= 1) println(n);
        var prev2 = 0
        var prev = 1
        var curi = 0
        for (i <- 2 to n)
        {
            println(prev2)
            curi = prev + prev2
            prev2 = prev
            prev = curi
        }
	}
}
```

Factorial

```scala
object Main {
	def main(args: Array[String]) {
		//Code
        val n = 5
        var fact = 1
        for(i <- 1 to n){
            fact *= i
            println(fact)
        }
	}
}
```

```scala
val numbers = List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
val evenNumbers = numbers.filter(number => number % 2 == 0)
println(evenNumbers)

val myList = List(1, 2, 3, 4, 5)
myList.foreach(println)
println(myList)
```

```scala
val myArray = Array(1, 2, 3, 4, 5)
myArray.foreach(println)

val myArray = Array(1, 2, 3, 4, 5)
val myList = myArray.toList
myList.foreach(println)
```

vote or not
```scala
object IfElseExample4 {
def main(args: Array[String]): Unit = {
val age = 20
if (age < 18) {
println("You are not yet an adult.")
} 
else if (age >= 18 && age < 65) {
println("You are an adult.")
} 
else {
println("You are a senior citizen.")
}}}
```

While loop
```scala
object WhileLoopExample1 {
def main(args: Array[String]): Unit = {
var i = 1
while (i <= 10) {
println(i)
i += 1
}}}
```

```scala
val myArray = Array(1, 2, 3, 4, 5)
val index = 2 // Index where the element should be inserted
val element = 10 // Element to be inserted

val newArray = myArray.patch(index, Array(element), 0)
```

```scala
val myList = List(1, 2, 3, 4, 5)
val index = 2 // Index where the element should be inserted
val element = 10 // Element to be inserted

val newList = myList.patch(index, List(element), 0)
```

```
def removeElement[A](list: List[A], element: A): List[A] = {
  list.filterNot(_ == element)
}

val myList = List(1, 2, 3, 4, 5)
val elementToRemove = 3

val newList = removeElement(myList, elementToRemove)
println(newList)
```

```scala
def checkNumber(number: Double): String = {
  if (number > 0) "Positive"
  else if (number == 0) "Zero"
  else "Negative"
}

val number = -5.3
val result = checkNumber(number)
println(s"The number $number is $result.")

```

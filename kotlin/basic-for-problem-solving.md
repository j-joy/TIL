### main class
```kotlin
fun main(args: Array<String>) {
    print("Hello, World!")
}
```

### Reads a line of input from the standard input stream
```kotlin
val line = readLine()
```
### Read a line as String and parse to other type
```kotlin
val num = readLine()!!.toInt();
```

### print
```kotlin
print();
```

### println
```kotlin
println();
```

### for loops
```kotlin
for (item in collection) print(item)

for (item: Int in ints) {
    // ...
}
```

### if expression
In Kotlin, if is an expression, i.e. it returns a value.
```kotlin
// Traditional usage
var max = a
if (a < b) max = b

// With else
var max: Int
if (a > b) {
    max = a
} else {
    max = b
}

// As expression
val max = if (a > b) a else b
```
if branches can be blocks, and the last expression is the value of a block:
```kotlin
val max = if (a > b) {
    print("Choose a")
    a
} else {
    print("Choose b")
    b
}
```

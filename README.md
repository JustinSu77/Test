---
Title: 'map'
Description: 'Map is a built-in data structure used to store data of the same or different data type in key-value pairs.'
Subjects:
  - 'Computer Science'
Tags:
  - 'map'
  - 'Data Structures'
CatalogContent:
  - 'learn-go'
  - 'paths/computer-science'
---

## What is a map?

A map is a built-in data structure that is used to store a collection of unordered key-value pairs that can be the same or different data type. It is Go's implementation of a Hash Table, which allows for efficient access, insertion, and deletion.

## Syntax

### Initializing an empty map

An empty map can be created using the `create` function and assigning it to a variable.

```pseudo
[variable_name] := create(map[key_data_type]value_data_type)
```

### Initializing a map with existing key-value pairs.

A map can also be initialized with key-values pairs using a map literal.

```pseudo
[variable_name] := map[key_data_type]value_data_type){key-1: value-1...}
```
 
### Accessing Items

A value in the map can  be accessed using its corresponding key value by putting the key in brackets.

```pseudo
[map_name][key_value]
```

The value that results from the code above can also be stored in a variable for later use.

```pseudo
[variable_name] := [map_name][key_value]
```

If a key does not exist, then the equivalent of zero will be returned based on the data type of the values in the map.
 
### Adding Items

Add new key-value pairs into the map by setting the new key value to a new value.

```pseudo
[map_name][new_key] = [new_value]
```

## Examples

### Create empty map

The following code will demonnstrate how to create an empty map and print it.

```go
package main

import "fmt"

func main() {
  // Create a empty map called emptyMap
  emptyMap := make(map[string]int)

  // Print map
  fmt.Println(emptyMap)
}
```

Output:

```shell
map[]
```

### Initialize a map with key-value pairs
The following code will demonstrate how to initialize a map with kep-value pairs and print. it

```go
package main

import "fmt"

func main() {
    
   // Initialize map gradebook with values
   gradebook := map[string]float32{"John": 85.2, "Ana": 95.6}
    
   // Print map gradebook
   fmt.Println(gradebook)
}
```

Output:

```shell
map[Ana:95.6 John:85.2]
```

### Access a key-value pair in the map

The following code will print out the corresponding value for the key "John"

```go
package main

import "fmt"

func main() {
    
   // Initialize map gradebook with values
   gradebook := map[string]float32{"John": 85.2, "Ana": 95.6}
    
   // Print out the value with key "John"
   fmt.Println(gradebook["John"])
} 

```
Output:

```shell
85.2
```

### Access and store a key-value pair in a variable

The following code will access the value in the map that has the corresponding key of "John". It will store the result in a variable called johnScore and print it.

```go
package main

import "fmt"

func main() {
    
   // Initialize map gradebook with values
   gradebook := map[string]float32{"John": 85.2, "Ana": 95.6}
    
   // Store the value that has a key of "Ana" in johnScore
   anaScore := gradebook["Ana"]
   
   fmt.Println(anaScore)
} 
```

```shell
95.6
```

### Accessing a key that does not exist

The following code will demonstrate what will returned as the value for a key that does not exist for a map with strings as keys and floats as values.

```go
package main

import "fmt"

func main() {
    
   // Initialize map gradebook with values
   gradebook := map[string]float32{"John": 85.2, "Ana": 95.6}
    
   // Store the value that has a key of "John" in johnScore
   johnScore := gradebook["David"]
   
   // Since "David" does not exist in the float 0 will be printed
   fmt.Println(johnScore)
}

```
Output:

```shell
0
```

### Adding a new key-value pair into a map
The following code will first print an initialized map. It will then add 2 more key-value pairs into the map and print it.

```go
package main

import "fmt"

func main() {
    
   // Initialize map gradebook with values
   gradebook := map[string]float32{"John": 85.2, "Ana": 95.6}
    
   // Print the initialized map
   fmt.Println(gradebook)
   
   // Add more key-value pairs
   gradebook["George"] = 76.4
   gradebook["Emma"] = 90
   
   // Print the map again
    fmt.Println(gradebook)
}
```

Output:

```shell
map[Ana:95.6 John:85.2]
map[Ana:95.6 Emma:90 George:76.4 John:85.2]
```

### Codebyte Example

The following code will summarize all the initialization and operations for maps that has been shown in this document.

```go
package main

import "fmt"

func main() {
  // Create empty map called m
  m := make(map[string]float32)
  
  // Print empty map m
  fmt.Println("Empty map m: ",m)
  
  // Add values to m
  m["Alex"] = 92.5
  m["Amanda"] = 85.2

  // Print map m
  fmt.Println("m with 2 added key-value pairs: ",m)
  
  // Create map with values that has key data type as string and value data type as double
  gradebook:= map[string]float32{"John" : 85.2, "Ana" : 95.6}

  // Output map gradebook
  fmt.Println("map gradebook: ",gradebook)
  
  // Access non-existing key gets  zero value
  fmt.Println("grade of Bob who is not in map gradebook: ",gradebook["Bob"])
  
  // Store the value of the key "Ana" into variable
  anaGrade := gradebook["Ana"]
  
  // Print the variable
   fmt.Println("Ana grade: ", anaGrade)
  
  // Add new key-value pairs into gradebook
  gradebook["Bob"] = 100
  gradebook["Elizabeth"] = 88.6


 // Output map gradebook with new values
 fmt.Println("map gradebook with 2 more values: ",gradebook)

}
```

Output: 

```shell
Empty map m:  map[]
m with 2 added key-value pairs:  map[Alex:92.5 Amanda:85.2]
map gradebook:  map[Ana:95.6 John:85.2]
grade of Bob who does not exist within map gradebook:  0
Ana grade:  95.6
map gradebook with 2 more values: map[Ana:95.6 Bob:100 Elizabeth:88.6 John:85.2]
```

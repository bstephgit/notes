# GO reading notes
see [https://github.com/shapeshed/golang-book-examples](https://github.com/shapeshed/golang-book-examples)
variables not explicity initialized are by default

*bool* is false by default if not assigned
*int* is zero

## Variable type: 

*reflect* pkg:
```go
    reflect.TypeOf(var)
```

### Type conversion
pkg *strconv*
* from string:
```go
strconv.ParseBool("true")
```
   
* from bool 
```go
    strconv.FormatBool(true) 
````

#### Type info: 
pkg reflect
```go
    reflect.TypeOf(var)
```
## variable declaration:
```go
var <nom-var> <type-var>
```
several var on same line: var s, t string = "foo", "bar"

* block different types:
```go
var (
	s string = "foo"
  	i int = 4
    )
```
* Lazy initialization: 
```go
<var-name> := <value> 
```
Rq: should only be used inside function


* constants: 
```go
const i int = 10"
```

## for statement:

1) for index := 0; index; index++ { } : use classical index
```
```

2) for index , value := range container { } : iterate through container with range keyword.
```go
for i,v:=range my_array{
	fmt.Printf("[elem at index %d is \"%s\"]",i,v)
}
```
## defer

executed after function execution.
```go
func test_defer(){

	defer fmt.Printf("print using defer\n")
	fmt.Printf("print in test defer\n")
}
```

## Array, Slice, Map

### Array:
length fixed at declaration
var nomvar [nb_elem] type

ex:
```go
var beatles[4] string
//initilaized in declaration
numbers := []{1, 2, 3, 4}
```

### Slice: 
Slices are not fixed size array.
```go
var my_slice = make([] type_var, size)
```
* access element: 
```go
my_slice[index]
```
* append element(s): 
```go
my_slice := append( my_slice, elem1[, elem2, etc...])
```
* deleting elem: 
```go
my_slice := append(my_slice[:2], my_slice[2+1:]...)
```
* copying: 
```go
copy( copy_slice, my_slice ) 
```
or to copy sub range:
```go
copy( copy_slice, my_slice[1:] ) 
```


### Map:
* initialization
```
var players = make(map[string]int)
```
* assignation
```go
players["cook"] = 32
* delete:
```go
delete(player,"cook")
```

## Struct
* declaration
```go
type Movie struct {
	Name string
	Rating float32
}
```
*instanciation
```go
m := Movie {
	Name: "Citizen Kane",
	Rating: 10,
}
```
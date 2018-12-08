# GO reading notes

variables not explicity initialized are by default

*bool* is false by default if not assigned
*int* is zero

## Variable type: 

*reflect* pkg:
```
    reflect.TypeOf(var)
```

### Type conversion
pkg *strconv*
* from string:
```
strconv.ParseBool
```
   
* from bool 
```
    strconv.FormatBool(true) 
````

#### Type info: 
pkg reflect
    reflect.TypeOf(var)

## variable declaration:
```
var <nom-var> <type-var>
```
several var on same line: var s, t string = "foo", "bar"

* block different types:
```
var (
	s string = "foo"
  	i int = 4
    )
```
* Lazy initialization: 
```
<var-name> := <value> 
```
Rq: should only be used inside function


* constants: 
```
const i int = 10"
```

## for statement:

1) for index := 0; index; index++ { } : use classical index
```
```

2) for index , value := range container { } : iterate through container with range keyword.
```
for i,v:=range my_array{
	fmt.Printf("[elem at index %d is \"%s\"]",i,v)
}
```
## defer

executed after function execution.
```
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
```
var beatles[4] string
//initilaized in declaration
numbers := []{1, 2, 3, 4}
```

### Slice: 
Slices are not fixed size array.
```
var my_slice = make([] type_var, size)
```
* access element: 
```
my_slice[index]
```
* append element(s): 
```
my_slice := append( my_slice, elem1[, elem2, etc...])
```
* deleting elem: 
```
my_slice := append(my_slice[:2], my_slice[2+1:]...)
```
* copying: 
```
copy( copy_slice, my_slice ) 
```
or to copy sub range:
```
copy( copy_slice, my_slice[1:] ) 
```


### Map:


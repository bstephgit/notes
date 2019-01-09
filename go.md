# GO reading notes
see [https://github.com/shapeshed/golang-book-examples](https://github.com/shapeshed/golang-book-examples)

### Index

#### [Variables](#variables)
* [Variable type](#variabletype)
* [Type conversion](#typeconversion)
* [Type info](#typeinfo)
* [Variable declaration](#variabledeclaration)

#### [For statement](#forstatement)

#### [Defer](#defer)

#### [Array, Slice, Map](#arrayslicemap)
* [Array](#array)
* [Slice](#slice)
* [Map](#map)

#### [Struct](#structtype)

#### [Methods and Interfaces](#methodsinterfaces)
* [Methods](#methods)
* [Interfaces](#interfaces)

---

## <a name='variables'>Variables</a>

variables not explicity initialized are by default

| Type | Value |
|-----:|-----:|
| *bool* | false |
| *Integer* | 0 |
| *Float* | 0.0 |
| *String* | "" |
| *Pointer* | nil |
| *Function* | nil |
| *Interface* | nil |
| *Slice* | nil |
| *Channel* | nil |
| *Maps* | nil |

### <a name='variabletype'>[Variable](#index) type

*reflect* pkg:
```go
    reflect.TypeOf(var)
```

#### <a name='typeconversion'>Type conversion</a>

pkg *strconv*

* from string:

```go
strconv.ParseBool("true")
```
   
* from bool 

```go
    strconv.FormatBool(true) 
````

#### <a name='typeinfo'>Type info</a>

pkg reflect

```go
    reflect.TypeOf(var)
```

### <a name='variabledeclaration'>Variable declaration</a>

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

## <a name='forstatement'>for statement</a>

1) for index := 0; index; index++ { } : use classical index

2) for index , value := range container { } : iterate through container with range keyword.
```go
for i,v:=range my_array{
	fmt.Printf("[elem at index %d is \"%s\"]",i,v)
}
```
## <a name='defer'>defer</a>

executed after function execution.
```go
func test_defer(){

	defer fmt.Printf("print using defer\n")
	fmt.Printf("print in test defer\n")
}
```

## <a name='arrayslicemap'>[Array, Slice, Map](#index)</a>

### <a name='array'>Array</a>

length fixed at declaration
var nomvar [nb_elem] type

ex:

```go
var beatles[4] string
//initilaized in declaration
numbers := []{1, 2, 3, 4}
```

### <a name='slice'>Slice</a>

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


### <a name='map'>Map</a>

* initialization

```
var players = make(map[string]int)
```
* assignation

```go
players["cook"] = 32
```

* delete:

```go
delete(player,"cook")
```

## <a name='structtype'>[Struct](#index)</a>

* declaration (Remark no comma for field separation)

```go
type Movie struct {
	Name string
	Rating float32
}
```

* instanciation (short variable assignment)

```go
//one line 
m := Movie { Name: "Citizen Kane", Rating: 10 }

//multiple line (last line must have comma ',')
m := Movie {
	Name: "Citizen Kane",
	Rating: 10,
}
```

or shorter

```go
m := Movie { "Citizen Kane", 10 }
```

or using dot notation with **var** keyword

```go
var m Movie
m.Name = "Citizen Kane"
m.Rating = 10
```

or with **new** keyword then dot notation assignment

```go
m := new(Movie)
m.Name = "Metropolis"
m.Rate = 0.99
```
* Nested struct(s)

```go
//here Struct1 nests Struct2
type Struct1 struct {
	Field1 string,
	Field2 Struct2
}

type Struct2 struct {
	Field1 int,
	Field2 string
}

//instance Struct1 type
s := Struct1 {
	Field1: "a string",
	Field2: Struct2 {
		Field1: 10,
		Field2: "nested string"
	}
}

```

* Comparison

use *==* or inequality *!=*

```go

type Drink struct {
	Name string
	Ice bool
}

func main() {
	a := Drink {
		Name: "Lemonade",
		Ice: true,
	}
	
	b := Drink {
		Name: "Lemonade",
		Ice: true,
	}
	if a == b { // is True
		fmt.Println( "True" )
	} else {
		fmt.Println( "False" )
	}
}

``` 

* Copying 

 1. Value

```go
a := Drink {
 	Name: "Lemonade",
	Ice: true,
}

b := a

b.Ice = false // b not equal to a

fmt.Printf("%+v , %+v\n", a, b) 

```
	
 2. Reference

```go
a := Drink {
 	Name: "Lemonade",
	Ice: true,
}

b := &a

b.Ice = false // b still equal to a

fmt.Printf("%+v , %+v\n", a, *b)
```
* Public and Private values

Public means that it is exported from function, method or package.
All members beginning with uppercase are public else private.

```go 
type MyStruct struct {
	Field string // Public
	otherField // Private: not available if imported in other method or package
}
```
* Checking type

With package **reflect**

```go 
import "fmt"
import "reflect"

a := Drink {
 	Name: "Lemonade",
	Ice: true,
}

fmt.Printf("%s\n", reflect.TypeOf(a)) // prints Drink
```

## <a name='methodsinterfaces'>[Methods and Interfaces](#index)</a>

### <a name='methods'>[Methods](#index)</a>

Methods are functions with type definition

* By Reference 

```go
func (var_name * Type) return_type {
	//code...
}
```

* By Value

```go
func (var_name Type) {  //var_name is a copy of the original parameter
	//code...
}
```
A method set is a list of methods in a file referring to a particular type.

### <a name='interfaces'>[Interfaces](#index)</a>

An interface specifies a method set with no implementation.

```go 
// example: a Robot interface
type Robot interface {
	PowerOn() err 
	PowerOff() err
}
```

Interface is then implemented 

```go 
type T850 struct {
	Name string
}

// T850 implements Robots interface methods
//Remark: the two functions must be implemented to use T850 as robot (see below)

func (a *T850) PowerOn() err {
	return nil
}

func (a *T850) PowerOff() err {
	return nil
}
```
Example of use case

```go

func Boot( r Robot ) error {
	return r.PowerOn()
}

r := T850
Boot(&r)

```

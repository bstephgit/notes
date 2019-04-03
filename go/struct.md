## <a name='struct'>[Struct](index.md)</a>

* <a name="decl">[declaration](index.md#struct_decl)</a> (Remark no comma for field separation)

```go
type Movie struct {
	Name string
	Rating float32
}
```

* <a name="inst">[instanciation (short variable assignment)](index.md#struct_inst)</a>

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
* <a name="nested">[Nested struct(s)](index.md#struct_nested)</a>

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

* <a name="comp">[Comparison](index.md#struct_comp)</a>

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

* <a name="copy">[Copying](struct_copy)</a>

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
* <a name="check">[Checking type](index.md#struct_check)</a>

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

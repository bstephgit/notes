
## [Variables](index.md#variables)

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

### [Variable type](index.md#variabletype)

*reflect* pkg:
```go
    reflect.TypeOf(var)
```

#### [Type conversion](index.md#typeconversion)

pkg *strconv*

* from string:

```go
strconv.ParseBool("true")
```
   
* from bool 

```go
    strconv.FormatBool(true) 
````

#### [Type info](index.md#typeinfo)

pkg reflect

```go
    reflect.TypeOf(var)
```

### [Variable declaration](index.md#variabledeclaration)

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


## <a name='index.md#variables'>Variables</a>

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

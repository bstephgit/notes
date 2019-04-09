## <a name='methodsinterfaces'>[Methods and Interfaces](index.md#mi)</a>

### <a name='methods'>[Methods](index.md#mi_methods)</a>

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

### <a name='interfaces'>[Interfaces](index.md#mi_interfaces)</a>

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

r := T850 { Name: "Terminator" }
Boot(&r)

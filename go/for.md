## <a name='forstatement'>for statement</a>

1) for index := 0; index; index++ { } : use classical index

2) for index , value := range container { } : iterate through container with range keyword.
```go
for i,v:=range my_array{
	fmt.Printf("[elem at index %d is \"%s\"]",i,v)
}
```
## <a name='deferxx'>[defer](#index)</a>

executed after function execution.
```go
func test_defer(){

	defer fmt.Printf("print using defer\n")
	fmt.Printf("print in test defer\n")
}
```

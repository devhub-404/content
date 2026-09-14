# Slices, Length, Capacity, and `append`

A slice is a descriptor over an underlying array with a length and capacity. Slicing creates another view over storage, while `append` extends the logical sequence and may allocate a new backing array when capacity is insufficient.

```go
values := make([]int, 0, 4)
values = append(values, 10, 20, 30)

fmt.Println(len(values), cap(values))
```

Because multiple slices can share one backing array, mutating through one can affect another. After `append`, always use the returned slice because the backing storage may have changed. Preallocate capacity when a useful estimate is known, but avoid guessing huge capacities without evidence.

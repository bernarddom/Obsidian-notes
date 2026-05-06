### Create a signal
```
const count = signal(0)
```

### Get signal value
```
console.log("The count is " + count())
```

### Set signal value
```
count.set(3)
```

### Update signal value
```
count.update(value => value + 1)
```

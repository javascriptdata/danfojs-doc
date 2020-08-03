---
description: Round a DataFrame to a variable number of decimal places.
---

# danfo.DataFrame.round

**parameter**: **axis**{0 or ‘index’, 1 or ‘columns’}, default 0

                  **return**: {DataFrame}



```javascript
let data = [[10.1, 2.092, 4.23], [360.232244, 180.0190290, 36.902612]]
let df = new DataFrame(data)
let expected = [[10.1, 2.092, 4.23], [360.232, 180.0190, 36.903]]
df.round(3)
```



```javascript
let data = [[10.1, 2.092, 4.23], [360.232244, 180.0190290, 36.902612]]
let df = new DataFrame(data)
let expected = [[10.1, 2.1, 4.2], [360.2, 180.0, 36.9]]
df.round(1)
```


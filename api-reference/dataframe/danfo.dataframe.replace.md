# danfo.DataFrame.replace

This function replaces values in a dataframe with other values dynamically

            **parameter:** {kwargs} "replace": the value you want to replace, "with": the new value you      

                               want to replace the older value with, inplace: Perform operation inplace or      

                                not.

            **return:** {Series}

**Example**

```javascript
 let data1 = [[10, 45, 56, 25], [23, 20, 10, 24]]
 let sf = new DataFrame(data1)
 let expected = [[-999, 45, 56, 25], [23, 20, -999, 24]]
 let df_rep = sf.replace({ replace: 10, with: -999 })
```






# targets-R-proj

# check for errors

```{r}
tar_manifest(fields = all_of("command"))
```

```         
# A tibble: 4 × 2
  name  command                    
  <chr> <chr>                      
1 file  "\"example-data/data.csv\""
2 data  "get_data(file)"           
3 model "fit_model(data)"          
4 plot  "plot_model(model, data)"  
```

# run the pipeline

```{r}
tar_make()
```

```         
▶ dispatched target file
● completed target file [0.104 seconds]
✔ skipped target data
✔ skipped target model
✔ skipped target plot
▶ ended pipeline [0.151 seconds]
```

# view the results

```{r}
tar_read(plot)
```

![](images/clipboard-2496913300.png){width="418"}

```{r}
tar_read(model)
```

```         
(Intercept)        Temp 
-146.995491    2.428703
```

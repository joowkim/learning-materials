### summarize some values for calculating mean, sd or something like that
```manilius %>% group_by(group) %>% summarise(across(everything(), sum))```


### ggviolin plot with jitter
```ggplot(dat, aes(x= response, y= Age, color = response)) + geom_violin(draw_quantiles = c(0.25, 0.5, 0.75)) + theme_classic() + geom_jitter(alpha = .2)```

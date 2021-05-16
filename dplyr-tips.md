### summarize some values for calculating mean, sd or something like that
```manilius %>% group_by(group) %>% summarise(across(everything(), sum))```

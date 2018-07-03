# R_Assignment-session-2.2
1.
Read multiple JSON files into a directory to convert into a dataset.
I have files text1, text2, text3 in the directory JSON.
solution...>

library(rjson)
filenames <- list.files("Users/Desktop/json", pattern="*.json", full.names=TRUE) 
myJSON <- lapply(filenames, function(x) fromJSON(file=x))

2. js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",
"opening_weekend_take": 1234, "year": 2011,
"release_date_wide": "2011-09-16", "gross": 59954
}'

>  library(rjson)
   data.frame(t(unlist(fromJSON(js))))

if(!require(readxl)){install.packages("readxl")}
library(readxl)
if(!require(dplyr)){install.packages("dplyr")}
library(dplyr)
if(!require(lubridate)){install.packages("lubridate")}
library(lubridate)
if(!require(tidyverse)){install.packages("tidyverse")}
library(tidyverse)
load("data_ml.RData")                  
head(data_ml, 6)
data_ml <- data_ml %>%
  distinct() %>% #remove duplicates
  filter(date > "1999-12-31",         # Keep the date with sufficient data points
         date < "2019-01-01") %>%
  arrange(stock_id, date)             # Order the data
training_set <- filter(data_ml, date < as.Date("2014-01-15"))
validation_set <- filter(data_ml, (date >= as.Date("2014-01-15") 
                                   & date < as.Date("2017-01-15")))
testing_set <- filter(data_ml, date >= as.Date("2017-01-15"))
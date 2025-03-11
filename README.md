# Research

```{r, include=FALSE}

# Set a CRAN mirror
options(repos = c(CRAN = "https://cran.r-project.org"))

setwd("/Users/mac/Downloads") #for mac
lungcancer <- read.csv("NCI_State_Lung_Cancer_Incidence_Rates.csv", header = TRUE) # header = TRUE tells R that your first row contains the names of the columns and should not be considered data values. 

suppressMessages(suppressWarnings(install.packages("tidyverse")))
suppressMessages(suppressWarnings(install.packages("dplyr")))
suppressMessages(suppressWarnings(install.packages("kableExtra"))) 
suppressMessages(suppressWarnings(install.packages("knitr"))) #Install the knitr package to activate kable function
install.packages("magrittr")

```

```{r, echo=FALSE}

library(tidyverse)
library(dplyr)
library(knitr)
library(kableExtra)


state_incidence_table <- lungcancer %>% 
arrange(desc(AllAge_B_AA_Rate)) %>% 
select(STATE_NAME, STATE_ABBR, AllAge_B_AA_Rate, AllAge_M_AA_Rate, AllAge_F_AA_Rate)

kable(state_incidence_table, col.names = c("STATE", "ABBR", "STATE RATE", "MALE RATE", "FEMALE RATE"), caption = "Lung Cancer Incidence Rates by State and Gender") %>%
kable_styling(full_width = TRUE, position = "center", font_size = 12) %>%
             row_spec(0, background = "lightgray") %>%
             row_spec(1:9, background = "lightcoral") %>%
             row_spec(10:42, background = "pink") %>%
             row_spec(43:51, background = "paleturquoise")


```



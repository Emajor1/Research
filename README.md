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




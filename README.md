607week6quiz
============

week6 quiz
# week6quiz.R
# [For your convenience], here is the provided code from Jared Lander's R for Everyone, 
# 6.7 Extract Data from Web Sites

install.packages("XML")
require(XML)
theURL <- "http://www.jaredlander.com/2012/02/another-kind-of-super-bowl-pool/"
bowlPool <- readHTMLTable(theURL, which = 1, header = FALSE, stringsAsFactors = FALSE)
bowlPool

# (1). What type of data structure is bowlpool? 
#its a dataframe with 10 observations and 3 variables
class(bowlPool)
#dataframe


# (2). Suppose instead you call readHTMLTable() with just the URL argument,
# against the provided URL, as shown below

theURL <- "http://www.w3schools.com/html/html_tables.asp"
hvalues <- readHTMLTable(theURL)

# What is the type of variable returned in hvalues?
hvalues
class(hvalues)
# hvalues is a list of 7 elements which are the tables contained in this url

# (3). Write R code that shows how many HTML tables are represented in hvalues
length(hvalues)

# (4). Modify the readHTMLTable code so that just the table with Number, 
# FirstName, LastName, # and Points is returned into a dataframe
hvalues1 <- readHTMLTable(theURL,which=1)
hvalues1

# (5). Modify the returned data frame so only the Last Name and Points columns are shown.
hvaluesLastPoints<-subset(hvalues1,select=c("Last Name","Points"))
hvaluesLastPoints
hvaluesLastPoints
View(hvaluesLastPoints)





# (6) Identify another interesting page on the web with HTML table values.  
# This may be somewhat tricky, because while
# HTML tables are great for web-page scrapers, many HTML designers now prefer 
# creating tables using other methods (such as <div> tags or .png files).
hvaluesMSDA<-readHTMLTable("http://sps.cuny.edu/programs/ms_dataanalytics")
hvaluesMSDA
#(the above contains 2 tables)
hvaluesdatagov<-readHTMLTable("http://catalog.data.gov/dataset")
#(the above is 0)
hvaluesNobelPrize<-readHTMLTable("http://www.nobelprize.org/nobel_prizes/facts/")
#the above contains 8 tables(i can see it from environment on Rstudio)
hvaluesNobelPrize
# first table
hvaluesNobelPrize[1]
length(hvaluesNobelPrize)
# (7) How many HTML tables does that page contain?
# it contains 8 tables

# (8) Identify your web browser, and describe (in one or two sentences) 
#I use Internet Explorer
# how you view HTML page source in your web browser.
# I right-click ,from the window displayed , I select View source


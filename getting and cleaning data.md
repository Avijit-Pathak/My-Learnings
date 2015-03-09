# 4 things required
1. The raw data
2. A tidy data set
3. A code book
4. Report the excat steps to show how you reached the tidy data

#Types of raw data
	*binary file
	*excel file
	*JSON data
	*hand entered

#Tidy data
*one variable per column
*differnet row
*one table for each kind of data

#1st command
~~~
if(!file.exists("name of the file)){
	dir.create("data") #creates the directory
}
fileUrl<-"save the Url here"
download.file(fileUrl,destfile="destination file name", method="curl(for Mac)")
dateDownload <- date() # stores the date of download
~~~

cameraData <- read.table("directory", sep="seperator", header=T/F) #to read the file in RAM


*another important parameter*
	*na.strings: set the character that represents the missing values
	*quote=""  : for empty data values

## Reading Excel File
	*Use the package xlsx
>library(xlsx)
>cameradData <- read.xlsx("directory",sheetIndex=1,header=T)

	* read.xlsx can also be used to read specific rows and columns using **colIndex rowIndex**
	* to use colIndex and rowIndex you first have to specify their values
	* read.xlsx2 is much faster

## Reading XML files
	* Stands for Extensible markup language.
	* highly used in internet
	* web scraping
1.Start by loading the XML package.

>library(XML)

>fileUrl <- "type the Url here"

>doc <- xmlTreeParse(fileUrl,useInternal=TRUE) #used to load the doc in the RAM

>rootnode <- smlRoot(doc) #wrapper element for the doc

>xmlName(rootNode) #gives the main heading

#### Subsetting can be used to acceses internal elements
>rootNode[[1]][[1]] .... so on

>xmlSApply(rooNode,xmlValue) #gets the xml value

	*XPath Language for better understanding of XML
 
>xpathSApply(rootNode,"//name",xmlValue) #gets all the elements tagged with name

>xpathSApply(rootNode,"//price",xmlValue)

## JSON
	*JAVAscript Object Notation

>library(jsonlite)
>jsonData <- fromJSON ("Url") #reading the JSON file
>names(jsonData)
>names(ssonData$owner) #access the owner column
>jsonData$owner$login #subsetting

### Writing data frames to JSON
>myjson <- toJSON(iris,pretty=TRUE) #converts the iris data set to json

>cat(myjson)

#### Helps to covert the file to be used by an API that uses JSON file

## data.table package




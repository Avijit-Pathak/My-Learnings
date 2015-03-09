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

	* read.xlsx can also be used to read specific rows and columns using *colIndex* *rowIndex*
	* to use colIndex and rowIndex you first have to specify their values
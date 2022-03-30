# Locacation Search

## Technologies used in the project
- .Net core 3.1
- .Net core Web API
- xUnit.net

## Assumptions
I assume that,
- the maxDistance and maxResults are mandatory
- the data source is the provided CSV file

## Project Architecture

![Architecture Layers](https://user-images.githubusercontent.com/6565759/135203100-073e38f9-21b9-4a4a-bf19-dc8280c83b1f.JPG)


## Design Considerations
- Data access layer is designed as a seperate module, therefore I can include new datasources in the future for optimal performance
- Included a web API with Open API documentation as the interface and seperated it with the business logic
- Cache settings and CSV file access can be controlled through appSettings
- Created Three APIs to test the performace. We can use the /getlocationsParallel API for the highest performance
- Added two csv files (given locations file and doubled locations file) to test the performance of the file reads

## Testing performance of file read methods

The testing was carried out to find out the optimal file read mechanism. Please find the results below. 

  ![PerformanceOfFileReads](https://user-images.githubusercontent.com/6565759/135200571-85092040-9af2-4300-90c5-2820bcb60903.JPG)
  
After some testing, I could conclude that the Parallel.For method performed better for increasing number of CSV lines. 

## Run the project

### Pre-requirements

Make sure you have installed the following to run the project:
- .Net core 3.1
- Visual Studio 2019

### Steps

#### Run in Local
- Open the project from visual studio 2019
- Check the appsettings.json for the CSV file name (should be "Resources\\locations(5).csv")
- Run the project (you should be able to view the open API documentation)





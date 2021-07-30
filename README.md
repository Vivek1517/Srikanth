Tools Used:
Programming Language: JAVA
Maven - Java Project Management Tool (We can run our tests with maven commands) And Helps to maintain the dependencies and inter dependencies for the project We can find all the dependenciess at https://mvnrepository.com
Cucumber-JVM - is a pure Java implementation of Cucumber that supports the most popular programming languages for the JVM. You can run it with the tool of your choice.
Selenium WebDriver - Web browser applications Automation Tool http://www.seleniumhq.org/download/
Pre-requisites: required softwares to run this project
JDK Installations:

Windows: http://docs.oracle.com/javase/8/docs/webnotes/install/windows/jdk-installation-windows.html
Mac: https://docs.oracle.com/javase/8/docs/technotes/guides/install/mac_jdk.html
Maven Installations: Download Maven from https://maven.apache.org/install.html and configure in the system please run mvn --version from command line to see mvn

Selenium WebDriver (we can add dependecies to POM.XML file)

Cucumber JVM (we can add dependecies to POM.XML file)

WebDriver Manager (to setup the browser)

Run The Tests from command line: Unzip the project folder Open command line bash, go to the project folder where you got pom.xml file and run the below command

To run the test runner file to triggers the tests mvn -Dtest=TestRunner test
To run all the scenarios you can use @smoke tag as below mvn clean test -Dcucumber.options= "-Dtags =@smoke"
To run specific scenario you can use @specificTagName tag as below mvn clean test -Dcucumber.options= "-Dtags =@filters"
Using IDE: we can use IntellijIdea or eclipse Download Intellij Idea Community Edition (for FREE) from: https://www.jetbrains.com/idea/download/ Make Sure you got below Plugins installed on Intellij Idea: Cucumber for java, Maven and JAVA is configured to Intellij Idea

Run the project Using IDE Make sure JAVA is configured to Intellij Idea and other plugins (Cucumber, Maven) Unzip the Project and Open the project folder in IntelliJ Idea IDE You can change the tags accordingly in TestRunner.java file and Run TestRunner.java class

Folder Structure

Test
├── src
|   ├──test
|   |  ├──Java
|   |      └── com.pom.pages
|   |             ├──BasePage   # Initialisation of Common Test Data or common methods
|   |             ├──HomePage   # Implementation of Page methods for CoinMarketCap Home Page
|   |             └──WatchListPage  # Implementation of Page methods for CoinMarketCap Watch List Page
|   |      └── com.test.commons
|   |             ├──PropertyFileReader  # To read data from Property File
|   |      └── com.test.runners
|   |             ├── TestRunner  # Controller of all the tests
|   |      └── stepdefs
|   |             ├── Hooks  # Implementation of Cucumber Hooks
|   |             ├── StepDefenitionsFrontEnd  # Implementation of Cucumber Step Definitions for front end tests
|   |             ├── StepDefenitionsBackEnd  # Implementation of Cucumber Step Definitions for back end tests
|   |  ├──resources
|   |      └── Features
|   |             ├── ViewAll.feature         # Frontend Task Test 1:
|   |             ├── WatchList.feature     # Frontend Task Test 2:
|   |             ├── Filter.feature          # Frontend Task Test 3
|   |             ├── PriceConversion.feature  # Back-end Task 1
|   |             ├── CurrencyInfo.feature     # Back-end Task 2
|   |             ├── AreMineable(backEndTask-3).feature  # Back-end Task 3 (Extra Points)
|   |      └── Screens    #To store failed scenarios screenshots
|   |      └── Test.properties    #To store constant details
├── target                         # Storage of results and reports (it will be autogenerated when you run the tests)
└── pom.xml                        # project object model file which maintains all the required dependecnies of project
└── Readme                         # Information about the project and Instructions to run the project
Test Reports:

After running the tests, CucumberReports are created and stored in /target/cucumber-reports/cucumber-pretty/index.html you can see the failure steps and details of failure on the reports, index.html can be opened in the browser
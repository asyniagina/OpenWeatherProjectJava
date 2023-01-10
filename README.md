Java 11 | Selenium | TestNG | Maven | POM | Rest Assured Project

This is a sample Java 11 AdoptOpenJDK | Selenium WebDriver | Maven | TestNG | Rest Assured project created in IntelliJ IDE, using Page Object Model and Generic Type.

Website https://openweathermap.org/ was used to create functional, API, and UI tests.

ci.yml file was used for the GitHub workflow

dorny/test-reporter@v1 was used to generate reports after each CI run


pom.xml dependencies used:

<dependencies>

    <dependency>
        <groupId>org.testng</groupId>
        <artifactId>testng</artifactId>
        <version>7.6.1</version>
    </dependency>

    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.5.3</version>
    </dependency>

    <dependency>
        <groupId>io.github.bonigarcia</groupId>
        <artifactId>webdrivermanager</artifactId>
        <version>5.3.0</version>
    </dependency>

    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.10</version>
    </dependency>

    <dependency>
        <groupId>com.fasterxml.jackson.core</groupId>
        <artifactId>jackson-databind</artifactId>
        <version>2.14.1</version>
    </dependency>

    <dependency>
        <groupId>io.rest-assured</groupId>
        <artifactId>rest-assured</artifactId>
        <version>5.3.0</version>
        <scope>test</scope>
    </dependency>

    <dependency>
        <groupId>org.json</groupId>
        <artifactId>json</artifactId>
        <version>20220924</version>
        <scope>test</scope>
    </dependency>

</dependencies>
API testing
For testing requests and responses DevTools type property was used 

DevTools devTools;

setUpDevTool(WebDriver driver)  method was created in the class CaptureNetworkTraffic  to capture the traffic:


public CaptureNetworkTraffic setUpDevTool(WebDriver driver) {
devTools = ((ChromeDriver) driver).getDevTools();
devTools.createSession();
devTools.send(Network.enable(Optional.empty(), Optional.empty(), Optional.empty()));

     return this;
}
org.openqa.selenium.devtools.v106.network.Network was used for traffic interception.

Class HttpURLConnection was used to send direct API calls and check responses.

Rest Assured library and POJO Model was used for testing and validating REST APIs.

Setup the project and execute tests locally
1. Install IntelliJ IDE:
   https://www.jetbrains.com/help/idea/installation-guide.html

2. Copy the HTTPS project link from the GitHub repository:
   https://github.com/asyniagina/OpenWeatherProjectJava.git

3. Clone a repository from the main menu:
   https://www.jetbrains.com/help/idea/cloning-repository.html#clone_project_from_main_screen

4. Go to the resources package, and copy local.properties.TEMPLATE file. Paste it to the resources package, and re-name the new file as local.properties

5. Execute test class or single test by opening the Test class, right-clicking on the green triangle, and choosing Run

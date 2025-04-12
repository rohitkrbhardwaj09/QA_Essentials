-# Module-1: Overview on Automation & Selenium

**1. Introduction to Automation** {#Introduction-to-Automation}

  - **Automation Testing**: Using tools/scripts to execute test cases automatically.
  - **Goal**: Increase test efficiency, coverage, and reduce human errors.
  - **Used For**: Regression, smoke, sanity, load testing, etc.
<hr/>

**2. Challenges in Manual Testing** {#Challenges-in-Manual-Testing}

 - Time-consuming & repetitive.
 - Error-prone (human mistakes).
 - Not suitable for large-scale or frequent regression testing.
 - No reusability of test cases.
 - Limited test coverage under tight deadlines.
<hr/>

**3. Overcoming Challenges with Automation** {#Overcoming-Challenges-with-Automation}

<table>
  <tr>
    <td>Challenge (Manual)</td>
    <td>Solution (Automation)</td>
  </tr>
  <tr>
    <td>Repetitive tasks</td>
    <td>Run scripts repeatedly, quickly</td>
  </tr>
    <tr>
    <td>Human errors</td>
    <td>Accurate and consistent test execution</td>
  </tr>
  <tr>
    <td>Less coverage</td>
    <td>Run many tests across environments/browsers</td>
  </tr>
  <tr>
    <td>Time-consuming</td>
    <td>Fast execution via tools like Selenium</td>
  </tr>
</table>
<hr/>

**4. Importance of Programming in Automation** {#Importance-of-Programming-in-Automation}

 - Required to write test logic, loops, conditions.
 - Enables:
   - Data-driven testing
   - Modular framework design
   - Use of OOPs concepts (Java)
 - Example:
  ```Java
    WebElement btn = driver.findElement(By.id("submit"));
      if (btn.isDisplayed()) {
        btn.click();
      }
  ```
<hr/>

**5. Introduction to Selenium** {#Introduction-to-Selenium}

 - Selenium is an open-source automation tool for web applications only.
 - Supports multiple browsers and languages.
 - Does not support desktop or mobile apps directly.
<hr/>

**6. Selenium Components** {#Selenium-Components}

📦 Selenium Suite:
<table>
  <tr>
    <td>Component</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Selenium IDE</td>
    <td>Record & playback tool, Firefox/Chrome extension</td>
  </tr>
  <tr>
    <td>Selenium RC</td>
    <td>Obsolete; used a server to communicate with browsers</td>
  </tr>
  <tr>
    <td>Selenium WebDriver</td>
    <td>Directly interacts with browsers using drivers</td>
  </tr>
  <tr>
    <td>Selenium Grid</td>
    <td>Runs tests in parallel across machines/browsers</td>
  </tr>
</table>
<hr/>

**7. Selenium WebDriver Architecture**

```plaintext
Test Script (Java)
      |
Selenium WebDriver API
      |
Browser Driver (ChromeDriver, GeckoDriver)
      |
Browser (Chrome, Firefox)
```
<hr/>

**8. Advantages(✅) & Disadvantaged(❌) of Selenium WebDriver**  {#Advantages-and-Disadvantages-of-Selenium-WebDriver}

**--Advantages of Selenium WebDriver--**

  ✅ Open-source and free

  ✅ Cross-browser support (Chrome, Firefox, Edge, etc.)

  ✅ Cross-platform (Windows, macOS, Linux)

  ✅ Language support (Java, Python, JS, etc.)

  ✅ Integration with TestNG, Maven, Jenkins, etc.

  ✅ Supports parallel testing via Grid

**--Disadvantages of Selenium WebDriver--**

  ❌ Only web application testing

  ❌ No built-in reporting

  ❌ No support for desktop/mobile apps (need Appium for mobile)

  ❌ Requires programming knowledge

  ❌ No built-in object repository

<hr/>
<hr/>
<hr/>

# **Module-4: Selenium WebDriver** {#Introduction-to-WebDriver-and-Architecture}

## **1. Introduction to WebDriver and Architecture**

Selenium WebDriver can be defined in three ways:

**1) WebDriver is one of the component in selenium.**
> Component of Selenium Suite:
> - Selenium Suite includes:
>   - Selenium IDE
>   - Selenium WebDriver
>   - Selenium Grid
> - WebDriver is the core component for automating web applications.

**2) WebDriver is a java interface.**
> - WebDriver is a Java interface containing:
>   - Public & static variables
>   - Public, default, and abstract methods
> - It is implemented by:
>   - RemoteWebDriver class, which is extended by:
>     - ChromeDriver
>     - FirefoxDriver
>     - EdgeDriver
>     - (etc., for other browsers)
> ```plaintext
> WebDriver (interface)
>     ↓
> RemoteWebDriver (class)
>     ↓
> ChromeDriver / FirefoxDriver / EdgeDriver (classes)
> ```

**3) WebDriver is an API( Application Programming interface)**
> - Acts as a bridge between:
>   - Java Program (Client/Presentation Layer)
>   - Browser (Action Target)
> - WebDriver exposes methods which are invoked from a Java program (e.g., using Eclipse).
> - It performs actions on the browser:
>   - Opening URLs
>   - Entering inputs
>   - Clicking buttons
> - Communication Protocol:
>   - Old: JSON wire protocol
>   - New (Selenium 4+): W3C protocol
<hr/>

## Environment Setup & WebDriver Configuration
**Two Approaches to Setup:**
- Manual Setup with JAR files
- Using Maven Project (Recommended)

📌 **1. Manual Setup using JAR Files**
Step-by-Step Process:
🔹 a. Download JAR Files
 - Selenium WebDriver consists of multiple classes, interfaces, and methods.
 - All these components are bundled into a .jar (Java ARchive) file.
 - Visit: https://www.selenium.dev
 - Navigate to Downloads section.
 - Choose Java as the language.
 - Download the latest version (e.g., 4.18.1) zip file.

🔹 b. Extract ZIP File
 - Extract the zip file to get a folder containing:
 - Selenium jar files
 - lib folder (contains dependency jars)

🔹 c. Create Java Project in Eclipse
 - Open Eclipse.
 - Create a new workspace (or use existing one).
 - Create a New Java Project:
 - Project Name: WebDriverProject
 - Uncheck the module-info.java option.
 - Finish setup.

🔹 d. Attach JARs to Java Project
 - Right-click on the project > Build Path > Configure Build Path.
 - Go to Libraries tab > Add External JARs.
   - Select:
     - All main Selenium jars.
     - All jars from the lib subfolder.
     - Click Apply and Close.

⚠️ Drawbacks of Manual Setup:
- Fully Manual Process:
  - Manually download jars.
  - Manually update if a new version is released.
- Maintenance Overhead:
  - Old jars must be removed and new ones added manually.
  - Not suitable for real-time projects.

🛠️ **2. Maven Project Setup (Preferred Approach)**

📝 Key Points:
- Maven is a build tool, not an IDE.
- Automates the download and update of dependencies using pom.xml.
- Preferred in real-time projects and CI/CD pipelines.

**Creating a Maven Project in Eclipse**
1. Open Eclipse IDE
2. Create a New Maven Project
  - Navigate to File > New > Project...
  - In the dialog, expand Maven and select Maven Project, then click Next.
3. Configure Project Settings
  - Choose the workspace location or accept the default.
  - Click Next to proceed.
4. Select an Archetype
  - Choose an archetype, such as maven-archetype-quickstart, and click Next.​
5. Define Project Coordinates
  - Group Id: e.g., com.example​
  - Artifact Id: e.g., my-maven-app​
  - Version: e.g., 1.0-SNAPSHOT​
- Click Finish to generate the project.
6. Project Structure
Eclipse will create a project with the following structure:
```plaintext
my-maven-app/
├── src/
│   ├── main/
│   │   └── java/
│   └── test/
│       └── java/
└── pom.xml
```
7. Add Selenium WebDriver dependency in pom.xml
- Search for Dependency:
  - Go to mvnrepository.com
  - Search for: selenium java
  - Click on the latest version (e.g., 4.18.1)
- Copy Dependency XML:
```xml
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>4.18.1</version>
</dependency>
```
- Paste in pom.xml:
```xml
<dependencies>
  <!-- All project dependencies go here -->
  <dependency>
    <groupId>org.seleniumhq.selenium</groupId>
    <artifactId>selenium-java</artifactId>
    <version>4.18.1</version>
  </dependency>
</dependencies>
```
- ctrl+s (save the file)
8. Update the Maven Project:
  - Right-click the project in Eclipse
  - Go to Maven > Update Project
  - Enable Force Update of Snapshots/Releases
  - Click OK

 **🧙 What Happens Next?**
 - Maven downloads all required JARs based on the added dependency
 - Adds them under Maven Dependencies in your project
 - No manual download or setup required

🧪 **Result**
- Project is now ready with Selenium WebDriver setup.
- All JAR files are linked automatically.

**🔁 Upgrading a Dependency**
- Go to pom.xml and change the version number
Example:
```xml
<version>4.19.0</version>
```
- Update the project again (Right-click > Maven > Update Project)

- Maven will:
  - **Remove old** version JARs
  - **Download new** version JARs
<hr/>

## Setting up WebDriver in Eclipse {#setting-up-webdriver-in-eclipse}

**Create a Java Class and Write a Sample Script**
- Right-click on src/main/java
 New > Package → Name it com.selenium.test
- Inside the package, create a new Java Class → TestLaunch

- Sample Code:
```Java
package com.selenium.test;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class TestLaunch {
    public static void main(String[] args) {
        // Set path to chromedriver (if not in PATH)
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");

        // Launch browser
        WebDriver driver = new ChromeDriver();

        // Open website
        driver.get("https://www.google.com");

        // Print title
        System.out.println("Page Title: " + driver.getTitle());

        // Close browser
        driver.quit();
    }
}

```
<hr/>

## Configuring WebDriver for Different Browsers {configure-webdriver}

✅ Supported Browsers
Selenium WebDriver supports the following major browsers:

**Chrome – ChromeDriver**

**Firefox – GeckoDriver**

**Edge – EdgeDriver**

**Safari – (macOS only)**

**Internet Explorer – (deprecated, use only if absolutely needed)**

###  Setup using WebDriverManager (Recommended) {webdrivermanager}
```xml
<!-- Add to pom.xml -->
<dependency>
  <groupId>io.github.bonigarcia</groupId>
  <artifactId>webdrivermanager</artifactId>
  <version>5.6.2</version>
</dependency>
```

**⚙️ 1. Chrome Browser** {chrome}
```Java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import io.github.bonigarcia.wdm.WebDriverManager;

public class ChromeTest {
    public static void main(String[] args) {
        WebDriverManager.chromedriver().setup();
        WebDriver driver = new ChromeDriver();
        driver.get("https://google.com");
        driver.quit();
    }
}
```

**🦊 2. Firefox Browser** {firefox}
```Java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import io.github.bonigarcia.wdm.WebDriverManager;

public class FirefoxTest {
    public static void main(String[] args) {
        WebDriverManager.firefoxdriver().setup();
        WebDriver driver = new FirefoxDriver();
        driver.get("https://google.com");
        driver.quit();
    }
}
```

**🟦 3. Microsoft Edge Browser** {edge}
```Java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.edge.EdgeDriver;
import io.github.bonigarcia.wdm.WebDriverManager;

public class EdgeTest {
    public static void main(String[] args) {
        WebDriverManager.edgedriver().setup();
        WebDriver driver = new EdgeDriver();
        driver.get("https://google.com");
        driver.quit();
    }
}
```

**🍏 4. Safari Browser (macOS Only)** {safari-browser}
**Requirements:**
- Safari 10 or later
- Enable Allow **Remote Automation in Safari** → **Preferences** → **Develop**
```Java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.safari.SafariDriver;

public class SafariTest {
    public static void main(String[] args) {
        WebDriver driver = new SafariDriver();
        driver.get("https://google.com");
        driver.quit();
    }
}
```

**🔄 Switch Browser Dynamically (Example)** {switch-browser_dynamically}
```Java
public class CrossBrowserTest {
    public static void main(String[] args) {
        String browser = "chrome"; // change to firefox, edge, etc.
        WebDriver driver;

        switch (browser.toLowerCase()) {
            case "chrome":
                WebDriverManager.chromedriver().setup();
                driver = new ChromeDriver();
                break;
            case "firefox":
                WebDriverManager.firefoxdriver().setup();
                driver = new FirefoxDriver();
                break;
            case "edge":
                WebDriverManager.edgedriver().setup();
                driver = new EdgeDriver();
                break;
            default:
                throw new IllegalArgumentException("Browser not supported");
        }

        driver.get("https://example.com");
        driver.quit();
    }
}

```
<hr/>

## **How to Create Automated Test Case in WebDriver?** {#automated-test-case}
### Automated Test Case Document

#### Test Scenario: Verify login functionality on the application

| Test Case ID | Test Case Description       | Test Steps                                                                 | Test Data                    | Expected Result                      | Actual Result | Status | Comments         |
|--------------|-----------------------------|----------------------------------------------------------------------------|------------------------------|--------------------------------------|----------------|--------|------------------|
| TC_Login_01  | Valid login with credentials | 1. Open the browser<br>2. Navigate to the login page<br>3. Enter valid username and password<br>4. Click on login | Username: user123<br>Password: pass123 | User should be logged in and dashboard displayed | As expected    | Pass   | -                |
| TC_Login_02  | Invalid login with wrong password | 1. Open the browser<br>2. Navigate to the login page<br>3. Enter valid username and invalid password<br>4. Click on login | Username: user123<br>Password: wrongpass | Error message displayed: "Invalid credentials" | As expected    | Pass   | -                |
| TC_Login_03  | Blank username and password | 1. Open the browser<br>2. Navigate to the login page<br>3. Leave username and password blank<br>4. Click on login | Username: ""<br>Password: "" | Error message displayed: "Username and password required" | As expected    | Pass   | Validation works |
| TC_Login_04  | Valid username, blank password | 1. Open the browser<br>2. Navigate to the login page<br>3. Enter valid username and leave password blank<br>4. Click on login | Username: user123<br>Password: "" | Error message displayed: "Password required" | As expected    | Pass   | Validation works |
| TC_Login_05  | Blank username, valid password | 1. Open the browser<br>2. Navigate to the login page<br>3. Leave username blank and enter valid password<br>4. Click on login | Username: ""<br>Password: pass123 | Error message displayed: "Username required" | As expected    | Pass   | Validation works |


#### 📌 LoginTest.java
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginTestCases {
    public static void main(String[] args) throws InterruptedException {
        // Set the path to your WebDriver (update path as per your system)
        System.setProperty("webdriver.chrome.driver", "path/to/chromedriver");

        WebDriver driver = new ChromeDriver();

        // Test Case 1: Valid Login
        loginTest(driver, "user123", "pass123", "TC_Login_01");

        // Test Case 2: Invalid password
        loginTest(driver, "user123", "wrongpass", "TC_Login_02");

        // Test Case 3: Blank username and password
        loginTest(driver, "", "", "TC_Login_03");

        // Test Case 4: Valid username, blank password
        loginTest(driver, "user123", "", "TC_Login_04");

        // Test Case 5: Blank username, valid password
        loginTest(driver, "", "pass123", "TC_Login_05");

        driver.quit();
    }

    public static void loginTest(WebDriver driver, String username, String password, String testCaseId) throws InterruptedException {
        driver.get("https://example.com/login"); // replace with your login URL
        Thread.sleep(1000); // wait for page to load

        // Enter username
        WebElement usernameField = driver.findElement(By.id("username"));
        usernameField.clear();
        usernameField.sendKeys(username);

        // Enter password
        WebElement passwordField = driver.findElement(By.id("password"));
        passwordField.clear();
        passwordField.sendKeys(password);

        // Click login button
        driver.findElement(By.id("loginBtn")).click(); // change ID as needed
        Thread.sleep(1000);

        // Validation
        if (username.equals("user123") && password.equals("pass123")) {
            boolean isDashboardPresent = driver.getCurrentUrl().contains("dashboard"); // or check title
            System.out.println(testCaseId + ": " + (isDashboardPresent ? "PASS" : "FAIL"));
        } else {
            WebElement error = driver.findElement(By.id("errorMsg")); // change ID to match your app
            if (error.isDisplayed()) {
                System.out.println(testCaseId + ": PASS");
            } else {
                System.out.println(testCaseId + ": FAIL");
            }
        }
    }
}
```

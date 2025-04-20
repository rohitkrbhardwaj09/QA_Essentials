# Module-1: Overview on Automation & Selenium

## Introduction to Automation

  - **Automation Testing**: Using tools/scripts to execute test cases automatically.
  - **Goal**: Increase test efficiency, coverage, and reduce human errors.
  - **Used For**: Regression, smoke, sanity, load testing, etc.
<hr/>

## Challenges in Manual Testing

 - Time-consuming & repetitive.
 - Error-prone (human mistakes).
 - Not suitable for large-scale or frequent regression testing.
 - No reusability of test cases.
 - Limited test coverage under tight deadlines.
<hr/>

## Overcoming Challenges with Automation

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

## Importance of Programming in Automation

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

## Introduction to Selenium 

 - Selenium is an open-source automation tool for web applications only.
 - Supports multiple browsers and languages.
 - Does not support desktop or mobile apps directly.
<hr/>

## Selenium Components

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

## Selenium WebDriver Architecture 

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

## Advantages and Disadvantaged of Selenium WebDriver

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

---
---

# Module-4: Selenium WebDriver

## Introduction to WebDriver and Architecture

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

---

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

## Setting up WebDriver in Eclipse

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

<hr/>

## **Locating Elements Using HTML Tags and Attributes**
- Web elements on a page (like textboxes, buttons, links, images) are written using HTML.
- Each HTML element has a tag name (e.g., input, a, img, select) and attributes (e.g., id, name, class, placeholder).
- Example:
```html
<input type="text" name="search" placeholder="Search here" id="searchBox">
```
 From this, we can use attributes like id, name, or even tag name to locate elements.

 🔍 **Basic Locators in Selenium**
Selenium provides several built-in locators to find elements:
## 🔍 Basic Locators in Selenium

Selenium provides several built-in locators to find elements:

| Locator Method        | Description                                                  |
|-----------------------|--------------------------------------------------------------|
| `By.id`               | Locates element using the `id` attribute                     |
| `By.name`             | Locates element using the `name` attribute                   |
| `By.linkText`         | Locates anchor (`<a>`) elements with exact link text         |
| `By.partialLinkText`  | Locates anchor elements using partial text                   |
| `By.tagName`          | Locates element using tag name (e.g., `input`, `img`)        |
| `By.className`        | Locates using the `class` attribute                          |
| `By.xpath`            | Locates using XPath expressions                              |
| `By.cssSelector`      | Locates using CSS selectors                                  |


### 🏷️ Name Locator in Selenium

The **Name Locator** is used to identify elements using the `name` attribute of an HTML tag.

#### 📌 Syntax:
```java
driver.findElement(By.name("element_name"));
```

🧠 How it Works:
Selenium scans the DOM to find an element whose name attribute matches the given value.

✅ Example HTML:
```HTML
<input type="text" name="username" />
```

✅ Example Java Code:
```Java
WebElement usernameInput = driver.findElement(By.name("username"));
usernameInput.sendKeys("testUser");
```

📝 Notes:
- It's commonly used for form elements like input fields, radio buttons, and checkboxes.
- Make sure the name attribute is unique on the page, or it may return the first matching element only.

### 🏷️ ID Locator in Selenium

The **ID Locator** is one of the most preferred and fastest locators in Selenium. It is used to locate elements using the `id` attribute of an HTML element.

#### 📌 Syntax:
```java
driver.findElement(By.id("element_id"));
```

🧠 How it Works:
Selenium locates the web element that has a matching id attribute value.

✅ Example HTML:
```html
<input type="password" id="userPassword" />
```
✅ Example Java Code:
```java
WebElement passwordInput = driver.findElement(By.id("userPassword"));
passwordInput.sendKeys("securePass123");
```
📝 Notes:
- The id attribute should be unique on the web page.
- If multiple elements have the same id, Selenium will interact with the first match.
- This is generally the most efficient locator strategy.

### 🏷️ LinkText Locator in Selenium

The **LinkText Locator** is used to locate hyperlinks (i.e., `<a>` anchor tags) by matching the exact visible text of the link.

#### 📌 Syntax:
```java
driver.findElement(By.linkText("Exact Link Text"));
```

🧠 How it Works:
Selenium looks for anchor (<a>) elements that have text content exactly matching the provided string.

✅ Example HTML:
```html
<a href="/home">Go to Home</a>
```

✅ Example Java Code:
```java
WebElement homeLink = driver.findElement(By.linkText("Go to Home"));
homeLink.click();
```

📝 Notes:
- Case-sensitive — the link text must match exactly.
- Only works for <a> tags.
- Ideal for use when the link text is unique and static.

### 🔗 PartialLinkText Locator in Selenium

The **PartialLinkText Locator** is used to locate hyperlink elements (`<a>` tags) using a portion of the link's visible text.

#### 📌 Syntax:
```java
driver.findElement(By.partialLinkText("Partial Text"));
```

🧠 How it Works:
Selenium finds an anchor (<a>) element where the text includes the given substring.

✅ Example HTML:
```html
<a href="/profile">View Profile Page</a>
```

✅ Example Java Code:
```java
WebElement profileLink = driver.findElement(By.partialLinkText("Profile"));
profileLink.click();
```

📝 Notes:
-Useful when the link text is long or dynamic, and you only need to match a part of it.
- Only applicable to anchor (<a>) elements.
- Case-sensitive.

<hr/>
# CSS Selector
<hr/>
# XPath
<hr/>
# XPath Axes
<hr/>

# WebDriver Methods

### 🚗 WebDriver Methods in Selenium

WebDriver provides several **built-in methods** to control the browser and interact with web elements. These methods are part of the `WebDriver` interface and its associated classes like `WebElement`, `Options`, and `Navigation`.

---

## [Browser Control Methods](Notes.md#Browser-Control-Methods)

| Method                          | Description                                      |
|--------------------------------|--------------------------------------------------|
| [`get(String url)`](#get(String-url))              | Opens the given URL in the browser              |
| `getTitle()`                   | Returns the title of the current page           |
| `getCurrentUrl()`              | Returns the current URL                         |
| `getPageSource()`              | Returns the page source of the current page     |
| `close()`                      | Closes the current browser window               |
| `quit()`                       | Quits the entire browser session                |

---

## Navigation Methods

| Method                          | Description                                      |
|--------------------------------|--------------------------------------------------|
| `navigate().to(String url)`    | Navigates to the specified URL                  |
| `navigate().back()`            | Navigates one step back in the browser history  |
| `navigate().forward()`         | Navigates one step forward in the browser       |
| `navigate().refresh()`         | Refreshes the current page                      |

---

## Window and Frame Handling

| Method                                 | Description                                 |
|----------------------------------------|---------------------------------------------|
| `getWindowHandle()`                    | Returns current window handle               |
| `getWindowHandles()`                   | Returns set of all open windows             |
| `switchTo().window(String handle)`     | Switches control to the specified window    |
| `switchTo().frame(int/index/name)`     | Switches to a specific frame                |
| `switchTo().defaultContent()`          | Switches back to the main content           |
| `switchTo().alert()`                   | Switches to the alert box                   |

---
## Common Conditional Methods

These methods return `true` or `false` and are used to verify the state of a web element before interacting with it.

| Method         | Description                                                   |
|----------------|---------------------------------------------------------------|
| `isDisplayed()`| Checks if the element is **visible** on the page              |
| `isEnabled()`  | Checks if the element is **enabled** (interactable)           |
| `isSelected()` | Checks if the element is **selected** (checkboxes/radio)      |

---

## WebElement Interaction Methods

| Method                                  | Description                                     |
|-----------------------------------------|-------------------------------------------------|
| `findElement(By by)`                    | Finds a single web element                     |
| `findElements(By by)`                   | Finds a list of matching web elements          |
| `click()`                               | Clicks on the element                          |
| `sendKeys(String input)`                | Enters text into the input field               |
| `clear()`                               | Clears the input field                         |
| `getText()`                             | Returns the visible text of the element        |
| `getAttribute(String name)`             | Returns the attribute value                    |
| `isDisplayed()`                         | Checks if the element is visible               |
| `isEnabled()`                           | Checks if the element is enabled               |
| `isSelected()`                          | Checks if the element is selected              |
---

## Wait Methods

# 🧪 Example Usage

## Browser Control Methods

### get(String url)

```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		
		//It will maximize the window sizing
		driver.manage().window().maximize();
		
		//get() --> Opens the given URL in the browser
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		
		driver.quit();
	}
}
```
**Output: **
> ![image](https://github.com/user-attachments/assets/50489f74-f9e4-489e-b7cb-42128e642767)

### getTitle()
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		
		//It will maximize the window sizing
		driver.manage().window().maximize();
		
		//get() --> Opens the given URL in the browser
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		
		//Returns the title of the current page 
		String title = driver.getTitle();
		System.out.println(title);
		
		driver.quit();
	}
}
```
**Output: **
> ![image](https://github.com/user-attachments/assets/22cda751-1bc8-46b9-89f3-aeb084440892)

### getCurrentUrl() 
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		
		// It will maximize the window sizing
		driver.manage().window().maximize();
		
		// get() --> Opens the given URL in the browser
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		
		// Returns the current URL
		String currentURL = driver.getCurrentUrl();
		System.out.println(currentURL);
		
		driver.quit();
	}
}
```
**Output: **
> ![image](https://github.com/user-attachments/assets/7489b8d1-5708-4b17-b76d-01535abb0d52)


### getPageSource()
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		
		// It will maximize the window sizing
		driver.manage().window().maximize();
		
		// get() --> Opens the given URL in the browser
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		
		// Returns the page source of the current page
		String pg_src = driver.getPageSource();
		System.out.println(pg_src);
		
		driver.quit();
	}
}
```
**Output:**
> ![image](https://github.com/user-attachments/assets/e3c59352-387a-4ec1-923a-b184f7b3603a)

### close()
- It only closes the focused window (the one WebDriver is currently controlling).
- If there is only one browser window, it will behave like quit(), closing the session.
- If there are multiple tabs/windows, it will close the one in focus and keep the WebDriver session alive.
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WindowType;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		driver.get("https://example.com");

		// Open a new tab
		driver.switchTo().newWindow(WindowType.TAB);
		driver.get("https://google.com");

		// Close the current tab (Google)
		driver.close();

		// WebDriver still running, previous tab (example.com) remains
	}
}

```
**Output:** 
> Before: ![image](https://github.com/user-attachments/assets/268d70dd-a571-4009-87dc-ae5af9ed64e7)
> After: ![image](https://github.com/user-attachments/assets/f48c8af4-8ff9-4a6b-bae7-1e97183d7a78)

### quit():

- The `driver.quit()` method is used to **close all browser windows** and **safely end the WebDriver session**.
- Completely shuts down the WebDriver instance.
- Closes all open tabs/windows that were opened during the session.Frees up system resources used by the browser driver.
- Ends the driver-server communication.
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WindowType;
import org.openqa.selenium.chrome.ChromeDriver;

public class BrowserControlMethods {
	public static void main(String[] args) {	

		WebDriver driver = new ChromeDriver();
		driver.get("https://example.com");

		// Open another window
		driver.switchTo().newWindow(WindowType.WINDOW);
		driver.get("https://google.com");

		// Quit all windows and end the session
		driver.quit();


	}
}
```

### close() vs quit()
---
|Method | Close Current Window | Closes All Window | Ends WebDriver Session | 
|-------|----------------------|-------------------|------------------------|
| close() | ✅ Yes | ❌ No |	❌ No |
| quit() | ✅ Yes | ✅ Yes | ✅ Yes |

<hr/>

## Navigational Methods
Method | Description
--- | ---
navigate().to(String url) | Opens the specified URL (similar to driver.get())
navigate().back() | Simulates the browser's Back button
navigate().forward() | Simulates the browser's Forward button
navigate().refresh() | Refreshes the current web page
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class NavigationMethod{
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        
        driver.manage().window().maximize();

        // Navigate to the first URL
        driver.navigate().to("https://www.amazon.in");

        // Navigate to another URL
        driver.navigate().to("https://www.flipkart.com");

        // Navigate back
        driver.navigate().back();

        // Navigate forward
        driver.navigate().forward();

        // Refresh the page
        driver.navigate().refresh();

        driver.quit();
    }
}
```
---

## Window and Frame Handling

| Method                                 | Description                                 |
|----------------------------------------|---------------------------------------------|
| `getWindowHandle()`                    | Returns current window handle               |
| `getWindowHandles()`                   | Returns set of all open windows             |
| `switchTo().window(String handle)`     | Switches control to the specified window    |
| `switchTo().frame(int/index/name)`     | Switches to a specific frame                |
| `switchTo().defaultContent()`          | Switches back to the main content           |
| `switchTo().alert()`                   | Switches to the alert box                   |

### getWindowHandle()
The `getWindowHandle()` method is used to retrieve the **unique identifier (handle)** of the current browser window or tab.

🧠 **Key Points**
- Every browser window/tab opened by the WebDriver has a unique string handle.
- This handle is used to switch between windows or tabs.
- It returns a `String`.

**Example**
```java
package WebDriverMethods;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class WindowHandle {

	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		
		driver.get("https://www.google.co.in");
		String handle = driver.getWindowHandle();
		System.out.println("Window handle is: " +handle);

		driver.quit();
	}

}
```
**Output: **
> ![image](https://github.com/user-attachments/assets/7c7e7001-bd68-4582-8d73-b0bad13d3b3c)

### getWindowHandles()
The `getWindowHandles()` method is used to retrieve a **set of all window handles** opened by the WebDriver session.

🧠 **Key Points**
- It returns a `Set<String>` containing **all open window/tab handles**.
- These handles can be used to **switch between multiple windows or tabs**.
- Useful when handling popups, new tabs, or windows opened via automation.

**Example**
```java
package WebDriverMethods;

import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class WindowHandle {

	public static void main(String[] args) throws InterruptedException {
		
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		Thread.sleep(5000); //This is to wait for complete load
		driver.findElement(By.linkText("OrangeHRM, Inc")).click();
		
		Set<String> handle = driver.getWindowHandles();
		for (String string : handle) {
			System.out.println(string);
		}
		
		driver.quit();
	}

}
```
**Output:**
> ![image](https://github.com/user-attachments/assets/b3e8ba4f-d375-4408-965a-bd0081274c84)

### switchTo().window(String handle)
Used to **switch the WebDriver context** from the current window to another window or tab using its **window handle**.

**Example**
```java
driver.switchTo().window("windowHandle");
```

---
## Conditional Methods

These methods return `true` or `false` and are used to verify the state of a web element before interacting with it.

| Method         | Description                                                   |
|----------------|---------------------------------------------------------------|
| `isDisplayed()`| Checks if the element is **visible** on the page              |
| `isEnabled()`  | Checks if the element is **enabled** (interactable)           |
| `isSelected()` | Checks if the element is **selected** (checkboxes/radio)      |


### isDisplayed() 
Returns **true** if the element is visible in the DOM and displayed on screen else returns **false**.

Exapmple: We need to get the status of logo element of the webpage ![image](https://github.com/user-attachments/assets/8726f9de-de99-496e-bee1-cef215b12a44)

```java
package WebDriverMethods;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class ConditionalMethod {

	public static void main(String[] args) throws InterruptedException {
		
		WebDriver driver = new ChromeDriver();
		
		driver.manage().window().maximize();
		
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		//web page may take some time to load the webpage, in that case we might get an error
		// org.openqa.selenium.NoSuchElementException: no such element: Unable to locate element: {"method":"css selector","selector":"img[alt='company-branding']"}
		
		//so to prevent from that condition, we should use sleep
		Thread.sleep(3000);
		
		WebElement logo = driver.findElement(By.cssSelector("img[alt='company-branding']"));
		if(logo.isDisplayed()) {
			System.out.println("Logo is displaying");
		}else {
			System.out.println("Logo is not displaying");
		}
		driver.quit();
	}

}
```
**Output:**
> ![image](https://github.com/user-attachments/assets/5c48b4a1-84e2-4dc1-bf13-ffad2aa687fd)


### isEnabled(): 
Returns true if the element is enabled and interactable.

**Example:** We need to check google home page search is enabled/interactable or not
```java
package WebDriverMethods;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class ConditionalMethod {

	public static void main(String[] args) throws InterruptedException {
		
		WebDriver driver = new ChromeDriver();		
		driver.manage().window().maximize();
		
		driver.get("https://www.google.co.in");
		Thread.sleep(3000);
		
		WebElement ele = driver.findElement(By.xpath("//textarea[@id='APjFqb']"));
		if(ele.isEnabled()) {
			System.out.println("Enabled");
		}else {
			System.out.println("Not enabled");
		}	
		driver.quit();
	}
}
```
**Output:**
> ![image](https://github.com/user-attachments/assets/f7ab5628-1254-44af-9aea-4a788373555e)


### isSelected()
Returns **true** if the checkbox/radio button is selected.
```java
package WebDriverMethods;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class ConditionalMethod {

	public static void main(String[] args) throws InterruptedException {
		
		WebDriver driver = new ChromeDriver();
		driver.get("https://rahulshettyacademy.com/AutomationPractice/");
		Thread.sleep(3000);
		
		WebElement ele = driver.findElement(By.xpath("//input[@value='radio2']"));
		System.out.println("Before Selection: ..................");
		if(ele.isSelected()) {
			System.out.println("Selected");
		}else {
			System.out.println("Not Selected");
		}
		
		ele.click();
		System.out.println("After Selection: ................");
		if(ele.isSelected()) {
			System.out.println("Selected");
		}else {
			System.out.println("Not Selected");
		}			
		driver.quit();
	}
}
```
**Output:**
> ![image](https://github.com/user-attachments/assets/e40f0b01-6797-4ba7-8bfe-def2f1959558)
--- 

---

---

## Waits Method

**Q. How does selenium solves synchronization issue?**
**Q. What is Synchronization in Selenium??**

**Ans.** Synchronization in Selenium means **matching the speed of the Selenium script execution with the speed of the web application (AUT)**.
>	In simple terms:
>	**“Your script should wait just enough for elements to load, so it doesn't fail trying to interact with elements that aren't yet available.”**

=> **Without Synchronization:**
- Script may try to click or type on elements that aren’t yet visible or loaded.
- Causes NoSuchElementException, ElementNotInteractableException, etc.
- Example failure scenario:
```java
> driver.findElement(By.id("loginBtn")).click(); // Fails if button hasn’t loaded yet
```
==> It might through an exception saying
	- **NoSuchElementException()**
 	- **ElementNotFound()**

#### => **Thread.sleep()**
>	`Thread.sleep()` is a Java method that pauses the execution of your script for a specific amount of time — no matter what.

✅ Syntax:
```java
Thread.sleep(3000); // pauses for 3 seconds (3000 milliseconds)
```

**It’s like saying:**
> _“Stop everything and wait for 3 seconds, even if the element is already there.”_

⚠️ **Why Thread.sleep() is NOT recommended in Selenium?**
🚫 Problem	|	🔎 Explanation
---	|	---------------
⌛ Fixed Wait	|	It always waits the full time, even if the element loads earlier.
🐌 Slows Down Tests	|	Unnecessarily increases test execution time.
❌ No Condition Check	|	It doesn't check if the element is available or ready.
📉 Poor Reliability	|	Can fail if the page loads slower than the sleep time.

### 🕒 **_Wait Methods in Selenium WebDriver_**

In Selenium, **waits** are used to pause execution until a certain condition is met or until a specified time has elapsed. They help in handling dynamic web pages where elements take time to load.

##🔸 1. Implicit Wait

#### ✅ Description:
Tells WebDriver to wait for a certain amount of time when trying to find an element if it is not immediately available.

### 📌 Syntax:
```java
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
```

| **Advantages** |

1) Single time/One Statement		
2) It will not wait till maximum time if the element is available
3) Aplicable for all the elements
4) Easy to use

 | **Disadvantage** |
 1) If the time is not sufficient the you will get exception

**Example :**
```java
package WebDriverMethods;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class WaitMethod {

	public static void main(String[] args) {

		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		driver.manage().window().maximize();
		
		driver.findElement(By.xpath("//input[@placeholder='Username']")).sendKeys("Admin");
		
		driver.quit();
	}
}
```

**Interview Ques** : What is the default timeout of implicit wait?
**Answer**: 0 sec

---

## 🔸** 2. Explicit Wait** (_Recommonded_)

#### ✅ Description:
Waits for a certain condition to occur before proceeding further in the code.

📌 Syntax: 
```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("elementId")));
```

- Conditional based, it will not work more effectively.
- finding element is inclusive
- it will wait for condition to be true, then consider the time
- We need to write multiple statements for multiple elements

**Example:**
```java
package WebDriverMethods;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class WaitMethod {

	public static void main(String[] args) {

		WebDriver driver = new ChromeDriver();
		WebDriverWait waitt = new WebDriverWait(driver, Duration.ofSeconds(10));
		
		
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		driver.manage().window().maximize();
		
		// usage of explicit wait
		WebElement username = waitt.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@placeholder='Username']")));
		username.sendKeys("Admin");
		
		//before performing the action, we are waiting for the element to load then performing the action
		WebElement password = waitt.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//input[@placeholder='Password']")));
		password.sendKeys("admin123");
			
		WebElement loginButton = waitt.until(ExpectedConditions.elementToBeClickable(By.xpath("//button[normalize-space()='Login']")));
		loginButton.click();
		
		driver.quit();
	}
}
```
📌 Notes: Best Practices for Using Explicit Wait in Selenium
✅ Key Concepts:
- Explicit Wait is used to wait for a specific condition before proceeding with the next action in the script.
- It's often used to ensure an element is present, visible, or clickable before interacting with it.

💡 Best Practice Summary:
✔️ Apply Explicit Wait for One Element Per Page:
	- If you're on the same page, applying an explicit wait for just one key element is sufficient.
	- Once that one element is visible/loaded, it’s usually safe to assume that the rest of the elements on the page are also loaded.

✔️ Use One Explicit Wait per Page (During Navigation):
	-When navigating between multiple pages, apply explicit wait for one important element on each new page.
 	Example:
	Page 1 → Wait for Username field
	Page 2 → Wait for Dashboard header
	Page 3 → Wait for Form title

❌ What to Avoid:
- Do not apply explicit wait for every element (like all input boxes, buttons, checkboxes) on the page.
- It is redundant, tedious, and not necessary.
- Avoid overusing wait statements for elements on the same page.

🔁 In Case of Page Transitions:
- After clicking a button or submitting a form that redirects to a new page,
- Use explicit wait again for one element that confirms the new page has loaded.
```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import java.time.Duration;

public class PageTransitionWaitExample {

    public static void main(String[] args) {
        
        WebDriver driver = new ChromeDriver();
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));

        // Step 1: Open login page
        driver.get("https://opensource-demo.orangehrmlive.com/");
        driver.manage().window().maximize();

        // Step 2: Wait for username field and login
        WebElement username = wait.until(ExpectedConditions.visibilityOfElementLocated(By.name("username")));
        username.sendKeys("Admin");

        WebElement password = driver.findElement(By.name("password"));
        password.sendKeys("admin123");

        WebElement loginButton = driver.findElement(By.tagName("button"));
        loginButton.click();

        // Step 3: After login, wait for an element on the next page (Dashboard)
        WebElement dashboard = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//h6[text()='Dashboard']")));
        
        System.out.println("Dashboard loaded successfully!");

        driver.quit();
    }
}
```


# ⏳ Selenium Explicit Wait Conditions

Explicit Wait in Selenium waits for a certain condition to be true before proceeding. Use it to synchronize your script with the webpage's behavior.

---

## 📌 1. visibilityOfElementLocated(By locator)
- **Use when**: You want to wait until the element is present in the DOM **and** is visible on the page.
- ✅ Ideal for: Input fields, buttons before clicking or typing.

```java
wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("username")));
```

---

## 📌 2. elementToBeClickable(By locator)
- **Use when**: You need the element to be **visible and enabled** so it can be clicked.
- ✅ Ideal for: Buttons, links, checkboxes.

```java
wait.until(ExpectedConditions.elementToBeClickable(By.id("submit")));
```

---

## 📌 3. presenceOfElementLocated(By locator)
- **Use when**: You only need the element to be present in the DOM (even if hidden).
- ✅ Ideal for: Background validation, AJAX-loaded data not immediately visible.

```java
wait.until(ExpectedConditions.presenceOfElementLocated(By.name("hiddenElement")));
```

---

## 📌 4. titleIs(String title)
- **Use when**: You are waiting for the page title to exactly match the expected title.
- ✅ Ideal for: Confirming successful page navigation.

```java
wait.until(ExpectedConditions.titleIs("Dashboard - HRM"));
```

---

## 📌 5. titleContains(String partialTitle)
- **Use when**: The title is dynamic or contains expected keywords.
- ✅ Ideal for: Dynamic page transitions.

```java
wait.until(ExpectedConditions.titleContains("Dashboard"));
```

---

## 📌 6. urlToBe(String url)
- **Use when**: You expect to be navigated to an exact URL.
- ✅ Ideal for: Navigation testing.

```java
wait.until(ExpectedConditions.urlToBe("https://example.com/home"));
```

---

## 📌 7. urlContains(String partialUrl)
- **Use when**: The URL contains certain expected text.
- ✅ Ideal for: Redirects, login success checks.

```java
wait.until(ExpectedConditions.urlContains("dashboard"));
```

---

## 📌 8. alertIsPresent()
- **Use when**: You are waiting for a JavaScript alert to appear.
- ✅ Ideal for: Form validations, popups, confirm boxes.

```java
wait.until(ExpectedConditions.alertIsPresent());
```

---

## 📌 9. invisibilityOfElementLocated(By locator)
- **Use when**: You need an element to disappear before moving forward.
- ✅ Ideal for: Loading spinners, success messages.

```java
wait.until(ExpectedConditions.invisibilityOfElementLocated(By.id("loadingSpinner")));
```

---

## 📌 10. textToBePresentInElementLocated(By locator, String text)
- **Use when**: You want to wait until a specific text appears in an element.
- ✅ Ideal for: Status messages, dynamic content.

```java
wait.until(ExpectedConditions.textToBePresentInElementLocated(By.id("status"), "Success"));
```

---

## 📌 11. numberOfElementsToBe(By locator, int number)
- **Use when**: You are waiting for a specific number of matching elements.
- ✅ Ideal for: Tables, lists, search results.

```java
wait.until(ExpectedConditions.numberOfElementsToBe(By.className("rowItem"), 5));
```

---

## 📌 12. frameToBeAvailableAndSwitchToIt(By locator)
- **Use when**: You need to wait for an iframe to load, then switch to it.
- ✅ Ideal for: iframe-based applications.

```java
wait.until(ExpectedConditions.frameToBeAvailableAndSwitchToIt(By.id("frame1")));
```

---

# ✅ Tips:
- Always use `visibilityOfElementLocated` or `elementToBeClickable` for user interactions.
- Avoid using `Thread.sleep()` – it waits blindly.
- Explicit waits solve **synchronization issues** effectively.

---

## **FluentWait** in Selenium

## 🔹 What is FluentWait?
**FluentWait** is a type of dynamic wait in Selenium that waits for a condition to be true within a maximum time, checking at regular intervals.  
It also ignores specific exceptions while polling.

## 🔹 Why Use FluentWait?
- When elements take **variable time** to appear/load.
- To **customize** polling intervals.
- To **ignore specific exceptions** like `NoSuchElementException`.

## 🔹 FluentWait Syntax in Java

```java
Wait<WebDriver> wait = new FluentWait<>(driver)
    .withTimeout(Duration.ofSeconds(20))
    .pollingEvery(Duration.ofSeconds(1))
    .ignoring(NoSuchElementException.class);

WebElement element = wait.until(new Function<WebDriver, WebElement>() {
    public WebElement apply(WebDriver driver) {
        WebElement el = driver.findElement(By.id("dynamicElement"));
        if (el.isDisplayed()) {
            return el;
        }
        return null;
    }
});

```
### ✅ Real-Time Scenario Example — FluentWait in Selenium

### 📌 Scenario:
You are testing a **shopping site** where the "Add to Cart" button appears **only after a few seconds** once the product is selected due to AJAX loading.  
If you directly try to click it, you might get a `NoSuchElementException`.

---

### 💡 Objective:
Use `FluentWait` to wait until the "Add to Cart" button becomes visible and clickable.

---

### 🧪 Test Case:
1. Open the product page.
2. Wait for "Add to Cart" button to appear.
3. Click on it.

---

### ✅ FluentWait Implementation in Java:

```java
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.FluentWait;
import java.time.Duration;
import java.util.function.Function;

public class FluentWaitExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("https://example-shopping.com/product/123");

        // FluentWait configuration
        Wait<WebDriver> wait = new FluentWait<>(driver)
            .withTimeout(Duration.ofSeconds(20))
            .pollingEvery(Duration.ofSeconds(2))
            .ignoring(NoSuchElementException.class);

        // Wait until "Add to Cart" button is visible and return it
        WebElement addToCartBtn = wait.until(new Function<WebDriver, WebElement>() {
            public WebElement apply(WebDriver driver) {
                WebElement button = driver.findElement(By.id("add-to-cart"));
                if (button.isDisplayed() && button.isEnabled()) {
                    System.out.println("Button is visible and clickable now.");
                    return button;
                }
                return null;
            }
        });

        // Perform action
        addToCartBtn.click();
        System.out.println("Clicked on Add to Cart button!");

        driver.quit();
    }
}
```
### 🎯 **Key Points:**
- Custom wait time: 20 seconds
- Polling interval: Every 2 seconds
- Ignores NoSuchElementException
- Checks both isDisplayed() and isEnabled() conditions

### Difference Between FluentWait, WebDriverWait, and Implicit Wait

Wait Type	| Custom Polling	| Exception Handling	| Scope
---|---|---|---
Implicit Wait |	❌ No |	❌ No |	Applies to all elements globally
WebDriverWait |	✅ Yes | (default 500ms) |	✅ Yes (part of FluentWait) |	Specific to condition
FluentWait |	✅ Yes |	✅ Yes |	Highly customizable 

# 🧠 FluentWait – Tricky Interview Questions

---

## ❓ When do you prefer FluentWait over WebDriverWait?

### ✅ Answer: 
When I need more control over polling frequency and want to handle specific exceptions or conditions—for example, waiting for elements loaded via AJAX with unpredictable response time.

## ❓ Can you explain a real-time scenario where you used FluentWait?

### ✅ Answer: 
In one project, the "Place Order" button appeared only after payment options were loaded via AJAX. I used FluentWait to poll every 1 second and ignore NoSuchElementException until the button was interactable. This avoided flaky failures in our automation suite.

## ❓ Q: Can you explain the difference between FluentWait and WebDriverWait in detail?

### ✅ Answer:
WebDriverWait is actually a subclass of FluentWait with some defaults:
- **WebDriverWait** has default polling of **500ms**.
- **FluentWait** lets you **customize** everything: polling, timeout, exception handling.

> Use FluentWait when you need **fine-grained control** over the wait.

## ❓ Q: What happens if the condition in FluentWait is never met?

### ✅ Answer:
- If the condition is **never true** within the timeout, it throws a `TimeoutException`.

```java
Exception in thread "main" org.openqa.selenium.TimeoutException
```

## ❓ Q: What exceptions can you ignore in FluentWait?
### ✅ Answer:
You can ignore any runtime exception like:

- NoSuchElementException
- StaleElementReferenceException
- ElementNotVisibleException
```java
 .ignoring(NoSuchElementException.class)
 .ignoring(StaleElementReferenceException.class)
```

## ❓ Q: Can FluentWait be used for page load timeout?
### ✅ Answer:
No. FluentWait is for element conditions, not for page load.

👉 Use:
```java
driver.manage().timeouts().pageLoadTimeout(Duration.ofSeconds(30));
```

## ❓ Q: Can you use FluentWait with WebElement instead of WebDriver?
### ✅ Answer:
Yes, but it’s less common. While most FluentWait use-cases involve `WebDriver`, you can also use it with `WebElement` directly to **wait for internal changes** like text, visibility, or attribute changes **within the element itself**.
```java
new FluentWait<>(element)
```

📌 **Real-Time Scenario:**

You are testing a **real-time notification system**, where a `<div>` element’s **text changes** after an operation.  
Instead of re-finding the element again and again, use FluentWait on the existing `WebElement`.

## ✅ Example – Wait for text change using FluentWait on WebElement

```java
WebDriver driver = new ChromeDriver();
driver.get("https://example.com/notification");

// Step 1: Locate the element once
WebElement notification = driver.findElement(By.id("status-message"));

// Step 2: Wait for the element’s text to update
Wait<WebElement> wait = new FluentWait<>(notification)
    .withTimeout(Duration.ofSeconds(15))
    .pollingEvery(Duration.ofSeconds(2))
    .ignoring(NoSuchElementException.class);

wait.until(new Function<WebElement, Boolean>() {
    public Boolean apply(WebElement element) {
        String text = element.getText();
        System.out.println("Current text: " + text);
        return text.contains("Success");
    }
});
```

## ❓ Q: What is the default polling interval in FluentWait?
### ✅ Answer:
No default! You must set pollingEvery(...).
Unlike WebDriverWait which defaults to 500ms polling.

## ❓ Q: What are real-time failures where FluentWait helped?
### ✅ Answer:
- AJAX-loaded content delays
- Buttons that appear after animation
- Third-party scripts like payment gateways

🎯 FluentWait avoids test flakiness in these dynamic UIs.

## ❓ Q: Is FluentWait thread-safe?
### ✅ Answer:
No. Each thread should have its own instance of FluentWait.


--- 
---

# Selenium WebElements (Quick Reference Guide)

| WebElement Type     | HTML Tag(s)                        | Example                       | Selenium Handling (Java)                                          |
|----------------------|------------------------------------|-------------------------------|--------------------------------------------------------------------|
| [Text Box](Notes.md#Handling-Text-Boxes-in-Selenium-WebDriver)         | `<input type="text">`, `<textarea>` | Search bar, username field    | `element.sendKeys("text");`                                       |
| [Password Field](Notes.md#Handling-Password-Fields-in-Selenium-WebDriver)   | `<input type="password">`         | Login form password           | `element.sendKeys("password");`                                   |
| [Radio Button](Notes.md#Handling-Radio-Buttons-in-Selenium)     | `<input type="radio">`            | Gender selection              | `if (!element.isSelected()) element.click();`                      |
| [Checkbox](Notes.md#Handling-Checkboxes-in-Selenium)         | `<input type="checkbox">`         | Agree to terms, filters       | `if (!element.isSelected()) element.click();`                      |
| [Button](Notes.md#Handling-Buttons-in-Selenium-WebDriver)           | `<button>`, `<input type="submit">`, `<input type="button">` | Submit, Save buttons | `element.click();`                                                |
| **Dropdown (Select)**| `<select>`                        | Country list                  | `new Select(element).selectByVisibleText("India");`               |
| [Hyperlink (Link)](Notes.md#Handling-Hyperlinks-in-Selenium) | `<a>`                             | Navigation links              | `element.click();` or `element.getAttribute("href");`             |
| **Image**            | `<img>`                           | Product image                 | `element.getAttribute("src");`                                    |
| **Label / Text**     | `<label>`, `<p>`, `<span>`, `<div>` | Static text, headers         | `element.getText();`                                              |
| **Table**            | `<table>`, `<tr>`, `<td>`         | Data grids                    | `List<WebElement> rows = element.findElements(By.tagName("tr"));` |
| **List Items**       | `<ul>`, `<ol>`, `<li>`            | Menus, lists                  | `List<WebElement> items = element.findElements(By.tagName("li"));`|
| **iFrame**           | `<iframe>`                        | Embedded frame, ads           | `driver.switchTo().frame(element);`                               |
| **Date Picker**      | `<input type="date">` or custom   | Calendar widget               | `element.sendKeys("2025-04-19");` (varies for custom pickers)     |
| [Alert](Notes.md#Handling-Alert-Boxes-in-Selenium-WebDriver) | dummy | dummy | dummy |
| [Authentication popup](Notes.md#Handling-browser-based-authentication-popups-in-Selenium-WebDriver) | dummy | dummy | dummy |

# Notes:
- Always locate your WebElement first using `driver.findElement(By.…)` or `findElements()`
- For dropdowns, import: `import org.openqa.selenium.support.ui.Select;`
- Always check visibility and interactivity if unsure:  
  `element.isDisplayed();`, `element.isEnabled();`
- For iFrames: Switch back using `driver.switchTo().defaultContent();`

---

## Handling Text Boxes in Selenium WebDriver

---

## 🧪 What is a Text Box?

A **Text Box** is an HTML `<input type="text">` element that allows the user to enter text.

---

## 🧾 Common Operations on Text Boxes

| Operation                          | Method                                |
|-----------------------------------|---------------------------------------|
| Enter text into a textbox         | `sendKeys("value")`                   |
| Clear existing text               | `clear()`                             |
| Get entered text (if any)         | `getAttribute("value")`               |
| Check if text box is enabled      | `isEnabled()`                         |
| Check if text box is displayed    | `isDisplayed()`                       |

---

## 🌐 Example URL:  
`https://itera-qa.azurewebsites.net/home/automation`

---

## ✅ Real-Time Example – Text Box Handling

```java
WebDriverManager.chromedriver().setup();
WebDriver driver = new ChromeDriver();
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

driver.get("https://itera-qa.azurewebsites.net/home/automation");
driver.manage().window().maximize();

// Locate text boxes
WebElement nameBox = driver.findElement(By.id("name"));
WebElement emailBox = driver.findElement(By.id("email"));
WebElement phoneBox = driver.findElement(By.id("phone"));
WebElement addressBox = driver.findElement(By.id("address"));
WebElement passwordBox = driver.findElement(By.id("password"));

// Enter values
nameBox.sendKeys("Rahul Sharma");
emailBox.sendKeys("rahul@example.com");
phoneBox.sendKeys("9876543210");
addressBox.sendKeys("Mumbai, India");
passwordBox.sendKeys("Test@123");

// Clear a textbox
nameBox.clear();

// Check if textbox is displayed and enabled
if (nameBox.isDisplayed() && nameBox.isEnabled()) {
    nameBox.sendKeys("Amit Verma");
}

// Get the entered value for validation
String enteredName = nameBox.getAttribute("value");
System.out.println("Entered Name: " + enteredName);
```
### 🎯 Real-Time Scenario Use Case
✅ **Use Case:**
- Filling a user registration form where name, email, phone, address, and password are all required inputs.
- Simulate real user input.
- Clear fields if resetting form or validating edge cases.
- Validate post-entry using getAttribute("value").

### 🚫 Common Mistakes
- ❌ Using getText() instead of getAttribute("value") for input fields.
- ❌ Not checking if the element is enabled before interacting.
- ❌ Not using waits when the textbox is dynamically loaded.

## 💬 Tricky Interview Questions
### ❓ **Q:** How do you validate that text was correctly entered in a text box?
```java
String entered = element.getAttribute("value");
Assert.assertEquals(entered, "ExpectedValue");
```

### ❓ **Q:** Can you retrieve text from a disabled textbox?
### ✅ Answer: 
Yes, using getAttribute("value") even if the textbox is disabled.

### ❓ **Q:** How would you handle text box input if the field is dynamic?
### ✅ Answer:
You can use FluentWait or ExplicitWait to wait for textbox visibility:
```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
WebElement dynamicBox = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("username")));
dynamicBox.sendKeys("TestUser");
```

### 🧠 Best Practices
- Use **clear()** before **sendKeys()** to avoid appending.
- Always validate the value using **getAttribute("value")**.
- Use **Page Object Model (POM)** to abstract text box locators and actions.
- Prefer **By.id** for faster and reliable selection when available.

---

## Handling Password Fields in Selenium WebDriver

---

### 🔎 What is a Password Field?

A **Password Field** is an HTML input element with `type="password"`.  
It behaves like a regular text field but **masks** the input for security.

```html
<input type="password" id="password" name="password" />
```
### 🧾 Common Operations on Password Fields

Operation	|	Method
---	|	---
Enter password	|	sendKeys("yourPassword")
Clear password	|	clear()
Get entered value	|	getAttribute("value")
Check if enabled/displayed	|	isEnabled(), isDisplayed()

### 🌐 Real-Time Example Site
🔗 https://itera-qa.azurewebsites.net/home/automation

```java
WebDriverManager.chromedriver().setup();
WebDriver driver = new ChromeDriver();
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

driver.get("https://itera-qa.azurewebsites.net/home/automation");
driver.manage().window().maximize();

// Locate the password field
WebElement passwordField = driver.findElement(By.id("password"));

// Enter password
passwordField.sendKeys("Test@123");

// Validate entry
String enteredPassword = passwordField.getAttribute("value");
System.out.println("Entered Password: " + enteredPassword);

// Clear the password field
passwordField.clear();

// Re-enter if field is visible and enabled
if (passwordField.isDisplayed() && passwordField.isEnabled()) {
    passwordField.sendKeys("NewPass@456");
}
```

### 🎯 Real-Time Use Case
**Login Form Automation**
- In any real-time web app (e.g., Gmail, Facebook, banking apps), login involves:
- Entering email/username.
- Entering password (masked).
- Clicking Login/Submit.

**You must ensure:**
- Password is accepted properly.
- Validation for empty/invalid inputs works.
- Correct field masking.


### 🚫 Common Mistakes
- ❌ Using getText() – doesn't work on input fields.
- ❌ Forgetting to clear field before re-entering.
- ❌ Not handling dynamic loading of fields (use waits).

## 💬 Tricky Interview Questions
### ❓ Q: How can you verify what was typed into a password field?
### ✅ Answer: 
**Use:**
```java
String password = passwordField.getAttribute("value");
```

### ❓ Q: Can you extract the password value even if it's masked?
### ✅ Answer: 
Yes, using getAttribute("value") (Selenium reads DOM, not UI mask).

### ❓ Q: How would you handle login testing securely in automation?
### ✅ Answer: 
- Store passwords in environment variables or encrypted configs.
- Avoid printing passwords in logs.
- Use sendKeys() securely without hardcoding sensitive values.

**To handle login testing securely:**

1. **Do not hardcode credentials** in your script.
2. **Store sensitive data (username/password)** in:
   - Environment variables
   - `.properties` / `.env` files (secured and ignored in version control)
   - Encrypted storage
3. **Avoid printing passwords** or logging sensitive data.
4. Use `sendKeys()` securely after retrieving the data.

---

## 💻 Real-Time Example Using Environment Variables

### ✅ Step 1: Set Environment Variables

Set username and password on your system or CI pipeline.

**Windows (CMD):**
```cmd
set LOGIN_USER=rahul123
set LOGIN_PASS=Test@123
```

```java
public class SecureLoginTest {

    public static void main(String[] args) {

        WebDriverManager.chromedriver().setup();
        WebDriver driver = new ChromeDriver();

        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        driver.get("https://example.com/login");

        // Fetch credentials from environment variables
        String username = System.getenv("LOGIN_USER");
        String password = System.getenv("LOGIN_PASS");

        // Locate login elements
        WebElement usernameField = driver.findElement(By.id("username"));
        WebElement passwordField = driver.findElement(By.id("password"));
        WebElement loginButton   = driver.findElement(By.id("loginBtn"));

        // Enter credentials securely
        usernameField.sendKeys(username);
        passwordField.sendKeys(password);
        loginButton.click();

        // ❌ Don't do this
        // System.out.println("Entered password: " + password); // avoid logging sensitive info

        driver.quit();
    }
}
```

### 🔐 Why This is Important?
- ✅ Prevents accidental credential leaks in code repositories.
- ✅ Ensures secure test automation in CI/CD pipelines.
- ✅ Makes your tests portable and flexible (e.g., different users per environment).

### 🧠 Best Practices
- Use clear() before sendKeys().
- Always validate field state using isEnabled() and isDisplayed().
- Avoid hardcoding sensitive credentials in scripts.
- Use configuration files (like .properties, .env, or external files).

---

## Handling Radio Buttons in Selenium

### 📌 What is a Radio Button?

A **radio button** allows the user to **select only one option** from a set of predefined choices. They are grouped using the same `name` attribute.

## 🔍 Example HTML

```html
<form>
  <input type="radio" name="gender" value="male" id="male"> Male<br>
  <input type="radio" name="gender" value="female" id="female"> Female<br>
</form>
```

### 🧪 How to Handle Radio Buttons in Selenium
✅ **1. Select a Specific Radio Button**
```java
WebElement maleRadio = driver.findElement(By.id("male"));
maleRadio.click();
```

✅ **2. Check If a Radio Button is Selected**
```java
if (maleRadio.isSelected()) {
    System.out.println("Male option is selected");
}
```

✅ **3. Verify if a Radio Button is Displayed and Enabled**
```java
if (maleRadio.isDisplayed() && maleRadio.isEnabled()) {
    System.out.println("Radio button is ready to interact");
}
```

✅ **4. Handle a Group of Radio Buttons**
```java
List<WebElement> genderOptions = driver.findElements(By.name("gender"));

for (WebElement option : genderOptions) {
    String value = option.getAttribute("value");
    if (value.equals("female")) {
        option.click();
        break;
    }
}
```

### 🧠 Interview Questions

Question	| Answer
---	|	---
How do you select a radio button in Selenium?	|Use click() method on the WebElement.
How do you verify if a radio button is selected?	|	Use isSelected() method.
How to select a radio button by value?	|	Iterate the list and use getAttribute("value").
Difference between checkbox and radio button in Selenium?	|	Checkbox allows multiple selections; radio button allows one.
What if clicking a radio button doesn't work?	|	Use JavaScript click or check for overlays.

### ✅ Problem:
> You try to click a radio button using .click(), but nothing happens. This might be because:

- The element is hidden or covered by another element (overlay).
- There is some JavaScript handler blocking direct interaction.

### ✅ Solution:
Use **JavaScript Executor** to perform the click action forcefully.

💡 **Java Example with JavaScriptExecutor**
```java
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.By;

WebDriver driver = new ChromeDriver();
driver.get("https://itera-qa.azurewebsites.net/home/automation");

WebElement maleRadio = driver.findElement(By.id("male"));

JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("arguments[0].click();", maleRadio);
```

**✅ Bonus: Check if element is clickable or overlapped**
You can also try:
```java
try {
    maleRadio.click();
} catch (ElementClickInterceptedException e) {
    System.out.println("Radio button is not clickable directly. Using JS click.");
    js.executeScript("arguments[0].click();", maleRadio);
}
```

---

## Handling Checkboxes in Selenium

#### 🌐 Test URL:
`https://itera-qa.azurewebsites.net/home/automation`

## 📂 Java Class Used:
```java
package day24;

import java.time.Duration;
import java.util.List;
import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import io.github.bonigarcia.wdm.WebDriverManager;

public class HandleCheckboxes {
    public static void main(String[] args) throws InterruptedException {
        WebDriverManager.chromedriver().setup();
        WebDriver driver = new ChromeDriver();

        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        driver.get("https://itera-qa.azurewebsites.net/home/automation");
        driver.manage().window().maximize();

        List<WebElement> checkboxes = driver.findElements(
            By.xpath("//input[@class='form-check-input' and @type='checkbox']")
        );

        // Example operations below...
    }
}
```

## ✅ All Checkbox Operations Breakdown

### 1. ✅ Select Specific Checkbox
```java
driver.findElement(By.xpath("//input[@id='monday']")).click();
```
🧠 **Explanation:**
This selects only the checkbox for Monday using its unique id. Best when you know the exact checkbox to click.


### 2. ✅ Total Number of Checkboxes
```java
List<WebElement> checkboxes = driver.findElements(
    By.xpath("//input[@class='form-check-input' and @type='checkbox']")
);
System.out.println("Total number of checkboxes:" + checkboxes.size());
```
🧠** Explanation:**
Finds all checkbox elements using a common class & type. Useful to iterate over them dynamically.

### 3. ✅ Select All Checkboxes
```java
for (WebElement chkbox : checkboxes) {
    chkbox.click();
}
```
🧠 **Explanation:**
Useful when automating forms where all options must be selected (e.g., user selects all available days).

### 4. ✅ Select First N Checkboxes
```java
for (int i = 0; i < 2; i++) {
    checkboxes.get(i).click();
}
```
🧠 **Explanation:**
Selects only the first 2 checkboxes. Often used in test cases that verify minimum required selections.

### 5. ✅ Select Last N Checkboxes
```java
for (int i = checkboxes.size() - 2; i < checkboxes.size(); i++) {
    checkboxes.get(i).click();
}
```
🧠 **Explanation:**
For scenarios like: "User should be able to select the last 2 available options."

### 6. ✅ Uncheck All Selected Checkboxes
```java
for (WebElement chkbox : checkboxes) {
    if (chkbox.isSelected()) {
        chkbox.click();
    }
}
```
🧠 **Explanation:**
Best practice for resetting form state or ensuring checkboxes are in a known initial state.

### 🧠 Best Practices
- ✅ Use .isSelected() to avoid redundant clicks.
- ✅ Always prefer List<WebElement> for dynamic checkbox groups.
- ⏱ Use Thread.sleep() only for demo/debug, prefer Explicit Waits in real test cases.
- 🧼 Use .clear() or refresh the page if checkboxes behave unpredictably.

## 💬 Tricky Interview Questions
### ❓ **Q:** How do you check if a checkbox is already selected?
```java
if (checkbox.isSelected()) { // returns true/false }
```

### ❓ **Q:** How would you select checkboxes dynamically based on label?
```java
driver.findElement(By.xpath("//label[text()='Monday']/preceding-sibling::input")).click();
```

### ❓ **Q:** How would you write a reusable method to check multiple boxes?
```java
public void selectCheckboxes(WebDriver driver, String[] values) {
    for (String val : values) {
        driver.findElement(By.xpath("//input[@value='" + val + "']")).click();
    }
}
```
---

## Handling Buttons in Selenium WebDriver

### 📌 What is a Button?

A **button** is a clickable WebElement that performs an action when triggered — such as submitting a form, logging in, or navigating to another page.

## 🔍 Example HTML

```html
<button type="submit" id="loginBtn">Login</button>

<!-- Or -->
<input type="submit" id="registerBtn" value="Register">
```

### ✅ How to Click a Button in Selenium
**➤ Using .click() method**
```java
WebElement loginBtn = driver.findElement(By.id("loginBtn"));
loginBtn.click();
```

### ✅ How to Verify Button Properties
**➤ Check if Displayed and Enabled**
```java
if (loginBtn.isDisplayed() && loginBtn.isEnabled()) {
    loginBtn.click();
}
```

**➤ Check Button Text**
```java
String btnText = loginBtn.getText();
System.out.println("Button Text: " + btnText);
```

### 🧪 Real-Time Scenario Example
**Scenario: You want to click the "Submit" button after filling a form.**
```java
WebDriver driver = new ChromeDriver();
driver.get("https://itera-qa.azurewebsites.net/home/automation");

WebElement submitBtn = driver.findElement(By.xpath("//button[text()='Submit']"));

if (submitBtn.isEnabled()) {
    submitBtn.click();
} else {
    System.out.println("Submit button is disabled.");
}
```

### ⚙️ Click Using JavaScript (when .click() doesn't work)
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("arguments[0].click();", submitBtn);
```

### ✅ Validate Button is Disabled
```java
WebElement btn = driver.findElement(By.id("submit"));
boolean status = btn.isEnabled();
System.out.println("Button enabled? " + status);
```

### 🧠 Interview Questions

Question	|	Answer
---	|	---
How do you click a button in Selenium?	|	Use .click() method.
How to handle if the button is not clickable?	|	Use JavaScriptExecutor.
How to verify if a button is enabled or disabled?	|	Use .isEnabled() method.
What if button is hidden by overlay?	|	Use JS click or wait for overlay to disappear.
How to verify the button label or text?	|	Use .getText() for <button>, or .getAttribute("value") for <input type="submit">.

--- 

##  Handling Hyperlinks in Selenium

### 📌 What is a Hyperlink?

A **hyperlink** (`<a>` tag) is an anchor element used to navigate from one page to another.

🔍 **Example HTML**
```html
<a href="https://example.com/login" id="loginLink">Login</a>
```

### ✅ Locating a Hyperlink
**➤ By Link Text**
```java
WebElement loginLink = driver.findElement(By.linkText("Login"));
loginLink.click();
```

**➤ By Partial Link Text**
```java
WebElement loginLink = driver.findElement(By.partialLinkText("Log"));
loginLink.click();
```

**➤ By XPath or CSS**
```java
WebElement link = driver.findElement(By.xpath("//a[@id='loginLink']"));
link.click();
```

### 🔍 Real-Time Example: Click Link to Navigate
```java
WebDriver driver = new ChromeDriver();
driver.get("https://itera-qa.azurewebsites.net/home/automation");

WebElement testLink = driver.findElement(By.linkText("Test Automation"));
testLink.click();
```

### ✅ Get Link URL (href Attribute)
```java
String url = loginLink.getAttribute("href");
System.out.println("Link URL: " + url);
```

## 🧠 Interview Questions

Question	|	Answer
---	|	---
How do you click a link in Selenium?	|	Use .click() on an <a> tag element.
What's the difference between linkText and partialLinkText?	|	linkText matches exact text; partialLinkText allows partial match.
How to extract the destination URL of a link?	|	Use .getAttribute("href").
What if clicking link does not redirect?	|	Check for JS-based navigation or overlays.
Can you click link using JavaScript?	|	Yes, using JavascriptExecutor.

### ⚙️ Clicking Link with JavaScript (if .click() fails)
```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("arguments[0].click();", loginLink);
```

### 🔁 Iterate Over All Links on a Page
```java
List<WebElement> allLinks = driver.findElements(By.tagName("a"));

System.out.println("Total links: " + allLinks.size());

for (WebElement link : allLinks) {
    System.out.println(link.getText() + " --> " + link.getAttribute("href"));
}
```

---
## Handling Alert Boxes in Selenium WebDriver

This guide explains how to handle different types of alert boxes in Selenium with real-time examples and code comments for better understanding.

### ✅ Types of JavaScript Alerts

| Type              | Description                                     |
|-------------------|-------------------------------------------------|
| Simple Alert      | Contains a message and an OK button             |
| Confirmation Alert| Contains OK and Cancel buttons                  |
| Prompt Alert      | Input box along with OK and Cancel buttons      |
| Dynamic Alert     | Waits dynamically using `WebDriverWait`         |

### 🔗 Practice URL

👉 [https://the-internet.herokuapp.com/javascript_alerts](https://the-internet.herokuapp.com/javascript_alerts)

---

### 🚀 Java Code with All Alert Handling Examples

```java
package web_elements;

import java.time.Duration;
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class AlertDemo {

    public static void main(String[] args) throws InterruptedException {

        WebDriver driver = new ChromeDriver();
        WebDriverWait mywait = new WebDriverWait(driver, Duration.ofSeconds(10));

        driver.manage().window().maximize();
        driver.get("https://the-internet.herokuapp.com/javascript_alerts");

        // ---------------------------------------------
        // 1️⃣ Simple Alert - Only OK button
        // ---------------------------------------------
        driver.findElement(By.xpath("//button[normalize-space()='Click for JS Alert']")).click();
        
        // Switch to alert and accept
        Alert simpleAlert = driver.switchTo().alert();
        System.out.println("Alert message: " + simpleAlert.getText());
        simpleAlert.accept();
        System.out.println("✅ Simple Alert accepted\n");

        // ---------------------------------------------
        // 2️⃣ Confirmation Alert - OK and Cancel
        // ---------------------------------------------
        driver.findElement(By.xpath("//button[normalize-space()='Click for JS Confirm']")).click();

        Alert confirmAlert = driver.switchTo().alert();
        System.out.println("Confirm Alert message: " + confirmAlert.getText());

        // Option 1: Accept (click OK)
        // confirmAlert.accept();

        // Option 2: Dismiss (click Cancel)
        confirmAlert.dismiss();
        System.out.println("❎ Confirmation Alert dismissed\n");

        // Verification
        WebElement confirmResult = driver.findElement(By.id("result"));
        if (confirmResult.getText().contains("Cancel")) {
            System.out.println("✅ Cancel button was clicked - Confirmation verified");
        }

        // ---------------------------------------------
        // 3️⃣ Prompt Alert - Input box + OK/Cancel
        // ---------------------------------------------
        driver.findElement(By.xpath("//button[normalize-space()='Click for JS Prompt']")).click();

        Alert promptAlert = driver.switchTo().alert();
        System.out.println("Prompt Alert Text: " + promptAlert.getText());

        // Send input to the alert
        promptAlert.sendKeys("Welcome");
        promptAlert.accept(); // or promptAlert.dismiss();

        // Verify entered text displayed on the page
        String promptResult = driver.findElement(By.id("result")).getText();
        if (promptResult.contains("Welcome")) {
            System.out.println("✅ Prompt input accepted and verified");
        }

        // ---------------------------------------------
        // 4️⃣ Dynamic Alert Handling with WebDriverWait
        // ---------------------------------------------
        driver.findElement(By.xpath("//button[normalize-space()='Click for JS Prompt']")).click();

        // Wait until alert is present using explicit wait
        Alert waitAlert = mywait.until(ExpectedConditions.alertIsPresent());
        waitAlert.accept(); // Can also dismiss

        System.out.println("✅ Dynamic Alert handled using WebDriverWait");

        driver.quit();
    }
}
```

## 🧠 Interview Questions

Question	|	Answer
What if NoAlertPresentException is thrown?	|	Use ExpectedConditions.alertIsPresent() before switching
Can you send text to simple or confirmation alert?	|	❌ No, only prompt alerts support input
How do you verify alert text without clicking it?	|	alert.getText()

## 🔧 Tips & Tricks
- Always switch to alert using driver.switchTo().alert() before interacting.
- Use WebDriverWait if alert is triggered with delay.
- Prompt alerts only allow sendKeys() input.
- Use try-catch to handle unexpected or missing alerts gracefully.
```java
try {
    Alert alert = driver.switchTo().alert();
    alert.accept();
} catch (NoAlertPresentException e) {
    System.out.println("No alert to handle.");
}
```
## 💡 Real-Time Use Cases

Alert Type	|	Real Scenario Example
---	|	---
Simple Alert	|	Login warning, confirmation messages
Confirmation Alert	|	Deleting a record or logout prompt
Prompt Alert	|	Asking for a reason for rejection/confirmation
Dynamic Alert Wait	|	Alerts triggered after AJAX or server call

---

## Handling browser based authentication popups in Selenium WebDriver

### 🔗 Practice URL

👉 [https://the-internet.herokuapp.com/basic_auth](https://the-internet.herokuapp.com/basic_auth)

This is a browser-based authentication popup (also called a Basic Authentication dialog), which Selenium cannot handle using sendKeys() or alerts, because it's part of the browser, not the webpage DOM.

✅** Workaround to Bypass Basic Authentication**
You can pass the username and password in the URL like this:
```perl
https://username:password@your-url
```
### 💡 Working Example with Selenium:
```java
package web_elements;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class BasicAuthDemo {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();

        // Username and password are both "admin"
        driver.get("https://admin:admin@the-internet.herokuapp.com/basic_auth");

        // Validate success
        String pageSource = driver.getPageSource();
        if (pageSource.contains("Congratulations")) {
            System.out.println("✅ Authentication successful.");
        } else {
            System.out.println("❌ Authentication failed.");
        }

        driver.quit();
    }
}
```
### 📌 Output Page Expected:
Once authenticated, it should show:
> **Congratulations! You must have the proper credentials.**

### Asssignment
1) Click on login then handle alert : https://rediff.com/login/dologin

#### Solution
```java
...........
```

---

## Handling Frames in Selenium WebDriver
### ❓ What is a Frame?
### ✅ Answer"
- Frame is an HTML element (<frame> or <iframe>) that embeds another document (webpage) within the current HTML document.
- Selenium cannot access elements inside a frame directly — you need to switch into the frame first.

### Types of Frames:
1) Single Frame
2) Nested Frames
3) Multiple Frames

### Frame Handling Methods


Method	|	Description
---	|	---
driver.switchTo().frame(index)	|	Switch by index (0-based)
driver.switchTo().frame(nameOrId)	|	Switch by frame’s name or ID
driver.switchTo().frame(WebElement)	|	Switch using a WebElement
driver.switchTo().defaultContent()	|	Switch back to main page
driver.switchTo().parentFrame()	|	Switch back to immediate parent frame

### ✅ Best Practice
Always inspect the DOM and identify how many frames are present. You can switch based on index or WebElement for reliability.

### 🚀 Real-Time Example
Site: **https://ui.vision/demo/webtest/frames/**
This site has multiple frames. Each frame contains an input box.

### Java Program to Handle All 3 Frames
```java
package web_elements;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class FramesDemo {

	public static void main(String[] args) {


		WebDriver driver = new ChromeDriver();
		
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		driver.get("https://ui.vision/demo/webtest/frames/");
		driver.manage().window().maximize();
		
		// ---------- Frame 1 ---------------
		WebElement frame1 = driver.findElement(By.xpath("//frame[@src='frame_1.html']"));
	
		driver.switchTo().frame(frame1);
		driver.findElement(By.xpath("//input[@name='mytext1']")).sendKeys("Welcome");
		
		//switch back to the main window
		driver.switchTo().defaultContent();
	
		// ---------- Frame 2 ---------------
		WebElement frame2 = driver.findElement(By.xpath("//frame[@src='frame_2.html']"));
		driver.switchTo().frame(frame2);
		driver.findElement(By.xpath("//input[@name='mytext2']")).sendKeys("Text in field 2");
		
		//switch back to the main window
		driver.switchTo().defaultContent();
		
		// ---------- Frame 3 --------------
		WebElement frame3= driver.findElement(By.xpath("//frame[@src='frame_3.html']"));
		driver.switchTo().frame(frame3);

		//switching to the inner frame
		driver.switchTo().frame(0);

		//selecting option from the given form
		driver.findElement(By.xpath("//div[@id='i6']")).click();
		
		driver.quit();	
	}
}
```

### Notes:
### ❓ How to Count Frames on Page
### ✅ Answer
```java
List<WebElement> frames = driver.findElements(By.tagName("iframe"));
System.out.println("Total Frames: " + frames.size());
```

### Frame Handling - Interview Ready Points
- Selenium cannot interact with elements inside a frame unless switched.
- Always switch back using `defaultContent()` before accessing elements outside.
- Nested frames need two-step switching — outer → inner.

## Assignment
-------

1) https://ui.vision/demo/webtest/frames/
2) switch to 5th frame
3) Check logo presence in the inner frame

#### solution
```java
package web_elements;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class FrameAssignment {

	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		driver.manage().window().maximize();
		driver.get("https://ui.vision/demo/webtest/frames/");

		WebElement frame5 = driver.findElement(By.xpath("//frame[@src='frame_5.html']"));
		driver.switchTo().frame(frame5);
		
		driver.findElement(By.xpath("//a[normalize-space()='https://a9t9.com']")).click();
		
		boolean status = driver.findElement(By.xpath("//a[@id='logo']")).isDisplayed();
		if(status) {
			System.out.println("Logo is displaying");
		}else {
			System.out.println("Logo is not displaying");
		}
	}

}
```

--- 

## Handling Dropdown in Selenium WebDriver
There are multiple types of dropdowns in web development when working with Selenium:
## [1. Standard Dropdown (HTML Select Tag)](Notes.md#Standard-Dropdown)
✅ Identified by:
`<select>` HTML tag

`<option>` tags inside

🛠️ Handled using:
Selenium's `Select` class

💡 Example HTML:
```html
<select id="country">
  <option value="in">India</option>
  <option value="us">USA</option>
</select>
```
🚀 Handling:
```java
WebElement countryDropdown = driver.findElement(By.id("country"));
Select select = new Select(countryDropdown);
select.selectByVisibleText("India");
```

## 2. Custom Dropdown (Non-Select Dropdown)
❌ Not a <select> element
Custom-built using:

<div>, <ul>, <li>, <a>, or other tags

JavaScript or CSS for behavior

🛠️ Handled using:
Manual clicks

Locating and interacting with elements

💡 Example HTML:
```html
<div class="dropdown">
  <button>Choose</button>
  <ul>
    <li>Option 1</li>
    <li>Option 2</li>
  </ul>
</div>
```
🚀 Handling:
```java
driver.findElement(By.className("dropdown")).click(); // open dropdown
List<WebElement> options = driver.findElements(By.tagName("li"));
for (WebElement option : options) {
    if (option.getText().equals("Option 1")) {
        option.click();
        break;
    }
}
```

## [3. Bootstrap Dropdown](Notes.md#Bootstrap-Dropdown-Handling-with-Selenium)
✅ Identified by:
Built using Bootstrap framework

Uses <div>, <button>, <ul>, <li> (NOT <select>)

Styled and shown via JavaScript/CSS (not native browser dropdown)

🛠️ Handled using:
Manual click actions (like custom dropdowns)

💡 Example HTML:
```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" data-toggle="dropdown">
    Choose Country
  </button>
  <div class="dropdown-menu">
    <a class="dropdown-item" href="#">India</a>
    <a class="dropdown-item" href="#">USA</a>
  </div>
</div>
```
🚀 Handling:
```java
// Click to open dropdown
driver.findElement(By.className("dropdown-toggle")).click();

// Select the required item
List<WebElement> options = driver.findElements(By.className("dropdown-item"));
for (WebElement option : options) {
    if (option.getText().equals("India")) {
        option.click();
        break;
    }
}
```

4. Hidden Dropdown
✅ Identified by:
Dropdown is not visible on page load

May require hover, click, or JavaScript to display

Often used in complex UIs, dynamic menus, or autocomplete fields

🛠️ Handled using:
JavaScript executor

Actions class (hover/mouse movement)

Waiting for visibility

🚀 Example Handling:
```java
WebElement dropdown = driver.findElement(By.id("hiddenMenu"));

// Option 1: Hover using Actions
Actions action = new Actions(driver);
action.moveToElement(dropdown).perform();

// Option 2: Make visible using JavaScript
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("arguments[0].style.display='block';", dropdown);

// Then interact with dropdown items
driver.findElement(By.xpath("//li[text()='Option 1']")).click();
```

✅ Summary Table
Type | HTML Tag(s) | Identified By | Selenium Handling
--- | --- | --- | ---
Standard Dropdown | <select> | Native HTML dropdown | Select class
Custom Dropdown | <div>, <ul>, etc. | No <select>, JS/CSS based | Manual click + list find
Bootstrap Dropdown | <button>, <a> | Bootstrap class (dropdown) | Manual click + class based selector
Hidden Dropdown | Any (hidden via CSS) | Requires hover or JS to reveal | Actions class / JavaScript executor

---
## Standard Dropdown
A dropdown is a web element (`<select>` tag) that allows users to select one option from a list.
Selenium handles dropdowns using the Select class (from `org.openqa.selenium.support.ui` package).

### Select Class Methods
Method | Description
--- | ---
selectByVisibleText("Option") | Select using option's text
selectByIndex(index) | Select by index (0-based)
selectByValue("value") | Select by value attribute
getOptions() | Returns all options in the dropdown
getFirstSelectedOption() | Returns currently selected option
deselectAll() | Deselects all (only for multi-select)
isMultiple() | Returns true if dropdown supports multiple selections

**Example**
```java
package web_elements;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class DropDownDemo {

	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		
		driver.manage().window().maximize();
		
		driver.get("https://testautomationpractice.blogspot.com/");
		
		
		WebElement drpCountryEle = driver.findElement(By.xpath("//select[@id='country']"));
		Select drpCountry = new Select(drpCountryEle);
		
		//1) select by visible text
		drpCountry.selectByVisibleText("France");
		
		//2) select by index
		drpCountry.selectByIndex(5);
		
		//3) select by value
		drpCountry.selectByValue("japan");
			
		//4) select by contained visible text
		drpCountry.selectByContainsVisibleText("nada");
		
		//5) get all options
		List<WebElement> options = drpCountry.getOptions();
		for (WebElement optn : options) {
			System.out.println(optn.getText());
		}
		
		//6) get first selected option
		WebElement selectedOption = drpCountry.getFirstSelectedOption();
		System.out.println("Selected Option is: "+selectedOption.getText());
		
		//7) isMultiple
		if(drpCountry.isMultiple()) {
			System.out.println("Dropdown supports multi select");
			//8) de-select 
			drpCountry.deselectAll();
		}else {
			System.out.println("DropDown does not support multi select");
		}
		
		driver.quit();
	}
}
```
---
## Bootstrap Dropdown Handling with Selenium
### 📌 Concept Summary


### ✅ Operations Performed in the Program

Operation | Description
--- | ---
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10)) | Set global implicit wait.
driver.manage().window().maximize() | Maximize the browser window.
driver.get("URL") | Navigate to a specific page.
driver.findElement(By.xpath(...)).click() | Click on the dropdown toggle or an item.
driver.findElements(By.xpath(...)) | Capture a list of elements (all dropdown options).
op.getText() | Get the text content of each dropdown item.
op.click() | Click an individual option from the list.

**Program**: 
```java
package web_elements;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class DropDownBootstrap {

	public static void main(String[] args) {
		
		WebDriver driver = new ChromeDriver();
		
		// Set implicit wait and maximize the browser window
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
		driver.manage().window().maximize();
		
		// Navigate to the Bootstrap dropdown demo page
		driver.get("https://www.jquery-az.com/boots/demo.php?ex=63.0_2");

		// Click on the dropdown toggle to expand the options
		driver.findElement(By.xpath("//button[contains(@class, 'multiselect')]")).click();
		
		// Select a single option: Python
		driver.findElement(By.xpath("//ul//input[@value=\"Python\"]")).click();
		
		// Capture all dropdown options (checkbox labels)
		List<WebElement> options = driver.findElements(By.xpath("//ul//label[@class=\"checkbox\"]"));
		System.out.println("Total count of options are: " + options.size());
		
		// Print all dropdown options' visible text
		for (WebElement op : options) {
			System.out.println(op.getText());
		}
		
		// Select multiple options: Oracle, Java, MySQL
		for (WebElement op : options) {
			String option = op.getText();
			if (option.equals("Oracle") || option.equals("Java") || option.equals("MySQL")) {
				op.click();
			}
		}
		
		// TODO: Additional validation such as checking selected state or deselecting options
		// You can extend this logic using op.findElement(By.tagName("input")).isSelected()
		// or implementing deselect feature (by clicking again)
	}
}
```
---

## Auto-Suggest Dropdown Handling in Selenium

### 🔍 What is Auto-Suggest Dropdown?

Auto-suggest dropdowns dynamically show matching results as you type. These suggestions aren't part of a `<select>` element but are usually rendered in a list (like `<ul><li>` structure) and are visible in the DOM after typing.

Example: **Google search suggestions**.

### 🧠 Key Concepts

- DOM gets updated as you type.
- Suggestions are usually loaded with delay (Ajax/JavaScript).
- Need to wait (explicit or Thread.sleep) to ensure options are present.
- Located using dynamic XPath based on structure (`ul > li`).
- Cannot use `Select` class (not a `<select>` element).
- Loop through suggestions and match using `.getText()`.

---

### ✅ Methods Used

| Method | Description |
|--------|-------------|
| `sendKeys()` | Types in the input box to trigger suggestions |
| `findElements()` | Captures multiple list suggestions |
| `getText()` | Gets visible text of suggestion |
| `click()` | Clicks the desired suggestion |
| `Thread.sleep()` | Pauses to let suggestions load |
| `getTitle()` | Retrieves page title to validate navigation |

### 🌐 Demo Site

Use: [https://www.google.com](https://www.google.com)  
Search for: `Selenium`  
Expected suggestion: `selenium interview questions`  

### 🧪 Real-time Use Case

- Auto-suggest search (Google, Amazon)
- Tagging people in social apps
- City name auto-complete fields in travel portals

---

### ⚠️ Tips

- Always ensure suggestions are visible before clicking.
- Handle `StaleElementReferenceException` in dynamic content cases.
- Use normalized text for matching (handle case-sensitivity).

```java
package web_elements;

import java.time.Duration;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class DropdownAutosuggest {

    public static void main(String[] args) throws InterruptedException {

        WebDriver driver = new ChromeDriver();

        // Maximize browser and set implicit wait
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        driver.manage().window().maximize();

        // Navigate to Google
        driver.get("https://www.google.com/");

        // Enter search keyword to trigger auto-suggest dropdown
        driver.findElement(By.name("q")).sendKeys("Selenium");

        // Wait for suggestions to load
        Thread.sleep(3000);

        // Capture all suggestions from auto-suggest dropdown
        List<WebElement> suggestions = driver.findElements(By.xpath("//ul[@role='listbox']//li"));

        // Loop through each suggestion
        for (WebElement suggestion : suggestions) {
            String text = suggestion.getText();
            if (text.equalsIgnoreCase("selenium interview questions")) {
                suggestion.click(); // Click the matching suggestion
                break;
            }
        }

        // Wait for results to load
        Thread.sleep(5000);

        // Click on specific search result link
        driver.findElement(By.xpath("//h3[normalize-space()='Selenium Interview Questions and Answers']")).click();

        // Validate the page title
        if (driver.getTitle().contains("GeeksforGeeks")) {
            System.out.println("Test Passed");
        } else {
            System.out.println("Something went wrong");
        }

        driver.quit(); // Close the browser
    }
}
````

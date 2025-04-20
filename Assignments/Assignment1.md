Website to Test : [https://blazedemo.com/](https://blazedemo.com/)

## ✅ Test Scenarios

1) Select Departure and Destination Cities
2) Click on "Find Flights"
3) Identify and click the flight with the lowest price
4) Fill the passenger form with valid data
5) Click "Purchase Flight"
6) Validate the confirmation message

## ✅ Test Cases (in tabular format)

Test Case ID | Description | Steps | Expected Result
-------------|-------------|-------|----------------
TC01 | Select cities and navigate to flight list | Launch browser → Select departure and destination cities → Click Find Flights | Flight table is displayed
TC02 | Identify lowest priced flight | Fetch all price cells → Sort prices → Click corresponding "Choose This Flight" | Navigated to purchase form
TC03 | Fill and submit form | Fill name, address, city, state, zip, card info → Click Purchase | Confirmation page with message
TC04 | Validate success message | Capture and verify "Thank you for your purchase today!" message | Message displayed as expected

## Code:
```java

```

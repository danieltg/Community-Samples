# Getting Started
This starter kit is designed to get you up and running using the Quantum framework (powered by [QAF](https://github.com/qmetry/qaf)) within few simple steps, and enable you to start writing your tests using simple [Cucumber] (https://cucumber.io/).

Please refer to this link to know more about Quantum - https://github.com/Project-Quantum/Quantum-Starter-Kit

About this project - 

Feature files are created to cater for any app type, i.e., it could be executed on Native, Hybrid or Web. 

## Running sample scenario as is
Run a single Quantum sample scenario from the samples provided in the project.

The sample scenario is located under the _src/main/resources/scenarios_ folder.

1. Configure your cloud and credentials in the _application.properties_ file (under the top _resources/_ folder).
2. Run your test via the TestNG.xml file (testng_expenseTracker.xml) with tags (@expenseTracker) in the project pane.
3.The sample scenario opens device and web browser in parallel launches Expense tracker app, login into application, add expense and logout.

## Scenario execution:

Native/Hybrid/Web App
1. Login to application with valid credentials
2. Initiate TouchID/FingerPrint authentication incase of Native/Hybrid
4. Click on Add expense
5. Enter details like, (head, currency, category)
6. Attach receipt using Perfecto Image injection incase of Native/Hybrid and using customizationScript and customizationScriptArgs capabilities for web.
7. Save Expense
8. Logout from application


### Object Repository creation guidelines
1. Copy-Paste your test to the _.loc_ file.
2. Remove lines unrelated to69 objects. 
3. From each object related line, create a line formatted as <br>`objectname = locatortype=objectlocator`<br>For example <br>`edit.start = xpath=//*[@label="Start location"]`

### Testng guidelines

1. Under the _config/_ folder, open the _testng_expenseTracker.xml, with tags (@expenseTracker) 
2. verify it's the only one with a **true** _enabled_ property, to prevent the other test suites from NOT running in parallel.
3. Copy your feature/scenario tag to the _name_ property in the _include_ clause. Use a space-separated tags' list to include more scenarios and features.
4. Add a parameter specifying the type of device, or naming a specific one, to be used for your test execution, for example, <br>`<parameter name="driver.capabilities.model" value="iPhone.*"></parameter>`


## Parallel execution
To run all samples in parallel, you need to configure the _TestNG.xml_ file (testng_expenseTracker.xml), which is located under the _src/test/resources/config/_ folder.

1. For each of the test suites (enclosed within <test>...</test>), set the _enabled_ property value to **_true_**.
2. Run your test as before.
3. This would trigger 3 instances of web browser, one instance of ios device and two instances of android devices.

## Viewing test execution results in Perfecto Reporting

All the previous executions were recorded, and may be viewed in Perfecto execution center, Reporting.


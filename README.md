-BACKGROUND-

You have been requested to create an interface and back-end system for a local Internet Service Provider, Byte Size. The Byte Size specializes in providing clients with Fibre internet.

Below are the requirements for the application provided by Byte Size:




-GENERAL-

The application we need is a Fault Management application. The Customer Service Representatives (CSR’s) will be the main users of this system. Each CSR receives many phone calls from clients every day. The clients call and inform the CSR if they have a fault with their fibre connection. The CSR then logs the fault on the system.

You are tasked with creating this fault management system that allows the CSR’s to create, update, and delete faults. The system should allow the CSR’s to change the status of faults, and change the priority of faults. Faults can be categorized into either Software or Hardware related faults.

The backend of the system should use JSON objects to store Fault Data.

As a proof of concept for the application, the initial dummy Fault data can be obtained from the API endpoints listed below, and this data should be stored in variables.

The front-end of the system should be developed using HTML and CSS. External libraries, such as Bootstrap may be used in the front-end.

The main page, where all the faults are listed, should have a toast notification popup when a fault is older than 24 hours, and the fault has not been marked completed.

-DATA-

You will be required to make two API calls. One each for the existing Hardware Fault Data and Software Fault Data:

Hardware Fault Data API:
http://backend.restapi.co.za/items/hardwareFaults

Software Fault Data API:
http://backend.restapi.co.za/items/softwareFaults

The application needs to be able to add, remove and edit these faults from your local objects. Each time the application is started, the API calls need to be made and each API response is stored in its object.

Object Oriented Programming should be used for this project. External libraries like bootstrap and jQuery should also be used. You are welcome to use any other external libraries should you need them. Node.js must not be used in this project.

There must be a main class (Parent) for the Faults called “Fault” and classes that inherit (Children) from the main class called “HardwareFault” and “SoftwareFault” - These child classes should each take an object as an input parameter (An object containing the API data).

The parent class “Fault” has the following properties:

status
datetimeLogged
priority
assignedTechnician
The child classes “HardwareFault” and “SoftwareFault” inherits from the parent class and have the following unique properties:

HardwareFault:

age (This should be calculated as relative time, an hour ago, a month a go etc)
location
SoftwareFault:

softwareVersion
lastUpdated

-USER INTERFACE MOCK-UP-


The client would like the main page layout to look similar to this mock-up, with a table for the Hardware Faults and a table for the Software Faults:





The Logo for Byte Size can be found in the repository generated for you by git classroom.

-FUNCTIONALITY-


The below implementation should be done for hardware and software objects

Change Priority:

To change a Faults priority, the user should select the fault from the table and click the “Change Priority” button to be presented with a way to change the priority (low, medium, high). When the priority of a Software Fault is changed, the “lastUpdated” property should also be updated to the date and time the change was implemented. This should reflect in the Software Fault Table as well.

Change Status:

To change the status of a fault, the user should be able to select a fault from the table and click “Change Status” (Logged, In-Progress, Completed). When the status is changed to “Completed” the fault should not be displayed in the table anymore. Only “logged” or “In-Progress” faults should be displayed in the table. When the status of a Software Fault is changed, the “lastUpdated” property should also be updated to the date and time the change was implemented. This should reflect in the Software Fault Table as well.

Adding a Fault:

When a user clicks on the “Add Fault” button, they should be able to add a new Fault. Validation should be done on any inputted data so that values are saved correctly for each field (null or undefined values are not allowed). By default, the status of a new Fault should be set as “Logged”.

Delete a Fault:

 Occasionally it might be necessary to delete a fault that has been added to the tables. In such cases by clicking the “Delete Fault” button the user can deleted a selected fault. A confirmation Popup should be presented to the user before deleting the fault, where the user would need to confirm the deletion. This is to prevent accidental deletion.

Toasts:

The system should make use of toasts to alert the user of fault statuses:

After 1 hour: If a task status has not been updated from “Logged” to “In-Progress” and the Priority is “High” send a toast notification to inform the user to check in with the Technician assigned to the fault.
After 24 hours:  If a task status has not been updated from “Logged” to “In-Progress” and the Priority is either “Low” or “Medium” send a toast notification to inform the user to check in with the Technician assigned to the fault.

The toast notifications for both Hardware and Software tasks should contain:

id
datetimeLogged
priority
assignedTechnician
Digital Clock:

Create a clock() function that shows the current date and time. This should be displayed at the bottom right of the webpage as can be seen in the user interface mockup above and should update every second. The format of the date and time needs to be the same as in the mockup provided.

Below is a “mockup” of what the classes should look like:


 


Styling:

All custom styling added to the project needs to be in a separate CSS file called myStyles.css

Styling for the Webpage:

Table header:
Font: Consolas
Font colour: #000000
Background colour: #A5A5A5
Table Light row:
Background colour: #EDEDED
Table Darker row:
Background colour: #C9C9C9
Web page text elements (paragraphs, etc:
Font: Calibri
Font colour: #000000
Add Fault button:
Font: Consolas
Background colour: #A9D08E
Font colour: #000000
Change Priority button:
Font: Consolas
Background colour: #FFD966
Font colour: #000000
Change Status button:
Font: Consolas
Background colour: #BDD7EE
Font colour: #000000
Delete Fault Button:
Font: Consolas
Font color: #000000
Background color: #FF5050
Toast Notification:
Background colour: #FF5050
Hover animations should be present on all buttons.




-JIRA PROJECT MANAGEMENT-


You must create a “Reflection Report”, in the form of a PDF document named “Jira.pdf”.

This report must include the following:

Screenshots of project Sprints, Epics, and Issues, elaborating on why you chose to create these issues.
Screenshots of the project Roadmap, Board, Backlog, and elaborations on the progress of the project
A summary of the management of this project, explaining why some choices were made in the development of this web application. This section must discuss some of the more difficult tasks, and how the results were achieved. The reflection report section must be between 500-1000 words and can include additional screenshots of what is being addressed.
-GIT-




Your repository must have two folders in it:

“Web Application” folder for all the separate project code folders.
“Documentation” folder for the project documentation. (This folder is where your “Jira.pdf” file will be placed)
There must also be a “readme.md” file in your repository (Outside of the previously mentioned folders) which documents the location of the code files and includes complete instructions on how to install and run your web application, including any external libraries or plugins.

Example of private repository folders

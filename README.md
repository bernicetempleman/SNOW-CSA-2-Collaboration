# SNOW-CSA-2-Collaboration

Collaboration
- Task Management
- Notifications
- Reporting

## Task Management

### Task Table
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/concept/c_TaskTable.html

### Task Table Extension
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/table-administration/concept/table-extension-and-classes.html

### Create a Task
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/task/t_CreateATask.html

### Task Assignment

ServiceNow can automatically assign a task to a user or group based on pre-defined conditions by using Assignment Rules

The Assignment rules module allows you to automatically set a value in the assigned_to and assignment_group fields when a set of conditions occurs. An assignment rule must also meet these additional criteria to run:

- The task record has been created or updated. Assignment rules do not apply to unsaved changes on a form. 

- The task record must be unassigned. The record cannot have an existing value for either the assigned_to or assignment_group fields. Assignment rules cannot overwrite existing assignments (including assignments set by a default value or a previously run assignment rule). 

- The assignment rule is the first rule that matches the table and conditions. If more than one assignment rule matches the conditions, only the rule with the lowest order value runs. 


https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/concept/c_DefineAssignmentRules.html

### Task Table Fields
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/reference/r_ImportantTaskTableFields.html

### Task State Flows
https://docs.servicenow.com/bundle/rome-servicenow-platform/page/administer/state-flows/concept/c_StateFlows.html

### Task Approval
https://docs.servicenow.com/bundle/rome-servicenow-platform/page/administer/service-administration/reference/r_Approvals.html

### Task Communications Management
https://docs.servicenow.com/bundle/rome-servicenow-platform/page/administer/task-communication-management/concept/task-communications-management.html

### Task Journal fields
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/reference/r_JournalFields.html

### Task Reminders
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/concept/reminder-table.html

### Tools to drive Tasks
https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/task-table/reference/r_ToolsForDrivingTasks.html

These tools can be run on any table which extends Task.

- Approvals
Approvals can be generated to a list of Approvers, either manually or automatically, according to Approval Rules. Approvals can be incorporated into workflows or can stand alone. For more information, see Process approvals.

Approvals can be used on tables that do not extend Task.

- Assignments
Assignment rules can automatically assign tasks to users or groups, ensuring that the most appropriate team members handle the tasks. For more information, see Defining Assignment Rules.

- Service levels
Service level agreements can track the amount of time that a task has been open, to ensure that tasks are completed within an allotted time.

- Inactivity monitors
Inactivity monitors ensure that tasks do not fall by the wayside by notifying users when tasks have been untouched for a predefined period of time. For more information, see Setting Inactivity Monitors.

= Workflow
An administrator can specify a specific workflow process to apply to tasks that meet certain conditions. After a task is created that meets the conditions, the workflow applies an automated process to the task. The process is defined in the graphical Workflow Editor.

## Notifications
Use ServiceNow Notifications to manage system email, create system notifications, and configure how your system responds to inbound email.

Notifications are important communication tools that keep users informed of events that concern them. You can use email notifications and SMS to send and receive communication from within the system. Notifications are triggered by system events, but unlike business rules, require no scripting knowledge. 

Users can subscribe to notifications of interest or unsubscribe from notifications that they do not want with the subscription based notifications feature.

The subscription based notifications feature enables users to subscribe to notifications of interest or unsubscribe from notifications that they do not want. This feature also enables administrators to send mandatory notifications that users cannot block.

Notifications can be triggered by events in the platform, but unlike Business Rules, require no scripting knowledge and can also be created for conditions

A notification is a tool for alerting users that concern them have occurred, including 
- Email
- SMS
- Meeting Invitation
- Push Notifications

Received by 
- Configured users
- Voluntary Recipients

## Events
An Event is an indication to the ServiceNow processes that something notable has occurred.

 Events are caused by
   
- User actions
Logging in, approving a request, renaming an attachment
= Scripts
Business Rules, Workflows  

Note: The Event definitions are in the sys_event table. System Administrators can view the definitions using the System Policy > Events > Registry
Note: The most common ways of generating events are by Business Rules and Workflow activities

## email notification tasks
For email messages, an administrator writes a simple form email that is sent out every time a certain event occurs. For example, an email notification generated by an incident can contain information about who opened the incident, the incident's priority, and the description.

Users can enable or disable the email notifications for themselves. They can also define more specific rules regarding which email notifications to receive if subscription based notifications are active. Users who receive email notifications can respond to the email, which triggers an inbound email action. Inbound email actions are the other half of the communication functionality that email notifications provide. By responding to email notifications, users can interact with the system through their email provider, without logging in to the instance.

This follows the below 5 tasks approach
 Configure Email Properties
 Create Events and Business Rules
 Create Email Notifications
 Configure Email Addresses and Subscribe to Notifications
 Create or Update ServiceNow Records via Email

 Configure Email Properties
Configure your SMTP and POP server settings in the email properties. The default settings are intended for the ServiceNow mail server and need not be changed unless you intend to use your own SMTP or POP server.

 Create Events and Business Rules
If the events in the base system do not provide the necessary level of detail, or do not suit your customized instance, create custom events to trigger notifications.

 Create Email Notifications
	Create the email notifications for your users. The base ServiceNow system provides many 	useful notifications. Create new records or edit an existing notification if the default 	functionality does not suit your business needs. Edit the notification message either in 	the 	notification record or in the email template the notification uses.
	
 Configure Email Addresses and Subscribe to Notifications
	Users can subscribe to or unsubscribe from with the subscription based notifications feature. 	This provides users with the flexibility of configuring the email notifications they see and the 	delivery method.

 Create or Update ServiceNow Records via Email
Use inbound email actions to perform various actions in ServiceNow. Inbound email actions behave like business rules and use conditions and scripts to perform tasks. 

## SMS
Short messaging service (SMS) is the standard protocol used to deliver short text messages to cell phones. Most cell phones support SMS, even if they do not support more sophisticated messaging like email. 

Note: This is particularly useful when critical events require immediate attention and an email notification may be too slow.

SMS messages, unlike emails, are limited to extremely short text strings, 140 characters in most cases. To compensate for this limitation, subscription based notifications provide the SMS alternate field for the Email Template and Email Notifications forms. Administrators can use this field to enter brief messages for SMS notifications.
ServiceNow sends SMS messages through an SMTP gateway to the cell phone companies. The carriers then forward the information to the devices. If the cell phone provider has an SMTP gateway, it can send SMS messages.

To configure notifications for SMS devices, such as cell phones, perform the following tasks.

This follows the below 4 tasks approach:
 Create Events and Business Rules
 Create Notifications for Users
 Create an SMS Device
 Subscribe to the Notification

 Create Events and Business Rules
If the events in the base system do not provide the necessary level of detail, or do not suit your customized instance, create custom events to trigger notifications.

 Create Notifications for Users
	The base ServiceNow system provides many useful notifications. You can create new 	records or edit an existing notification if the base system functionality does not suit 	your business needs. You can edit the SMS notification message in the SMS 	alternate field in either the notification record  or in the email template the 	notification uses. The SMS alternate field enables you to configure SMS messages 	that meet the 140 character limit. Keep in mind, hyperlinks embedded into SMS	messages will not work correctly.
	
 Create an SMS Device
	Configure SMS devices and select the carrier in the Notification Preferences form

 Subscribe to the Notification
Allow users to subscribe or unsubscribe from notifications on their SMS device or block delivery of certain notifications in the Notification Preferences form

### PUSH
In addition to sending email and SMS notifications, an instance can send push notifications to mobile devices.
A push notification is a text message that appears on a user's mobile device to alert them about something important or to ask them to perform an action. Your instance supports push notifications.

Use push notifications to send messages to users when certain conditions are triggered on your instance, such as the assignment of an incident to the user. A push notification can even ask for a reply, and the instance can process the reply by acting on the related records. For example, you can have the instance send an approval request for a Change to a user. You can let the user approve or deny the Change by clicking a response button on the push notification. The user's response can then update the status of the Change record.

You can set up push notifications in a similar manner to email and SMS notifications. Determine:

 who to send the notification to
 when it should be sent
 what it should contain

By default, the ServiceNow mobile application supports push notifications. But you can also develop your own push application and configure your instance to send push notifications to it.

## Email basic setup
All production instances can send and receive email using ServiceNow-provided resources. The instance has an email address of instance@service-now.com.
![image](https://user-images.githubusercontent.com/12488769/148660343-c69ccd27-7393-44bb-8246-6bd12dd4b3e8.png)

### System Mailboxes
Email messages can be seen in the System Mailboxes menu, which gives you access to the system Inbox, Outbox, and Sent mail box.
The system mailboxes menu shows your current POP and SMTP status.
The System Mailbox is hosted by ServiceNow, who have sole access to the mailboxes. By default, once the instance pulls an email message, it is deleted from the mail server and stored in the application on the Email [sys_email] table.

 Inbound emails: All inbound mail is placed into the Inbox until it is processed. After it is cleared, the email moves to the Received state. If the email message matches the criteria in an inbound email action, the email is changed to Processed. If not, it is changed to Ready. If the system is restarted for any reason (such as during a system upgrade), all inbound mail waits on the external mail server until the system can request delivery.

 Outbound emails: All outbound mail is placed into the Outbox until it is processed. Once cleared, it is moved to Sent (if sent) or Skipped (not sent, as in the case of no valid recipients). If the system is restarted for any reason (such as during a system upgrade), all outbound mail waits in the instance database until the system comes online, and the scheduler looks for mail to deliver.

## SLA Notifications
SLA sends notifications at certain events defined in the workflow.



By default, SLA notifications are sent on three occasions:

 SLA is at 50% of the duration specified in the SLA Definition: Notification is sent to the user in the Assigned to field mentioned in the incident form.

 SLA is at 75% of the duration specified in the SLA Definition: Notification is sent to the user in the Assigned to field mentioned in the incident form and the manager of the user.

 SLA is breached: Notification is sent to the user in the Assigned to field mentioned in the incident form and the manager of the user.

## Inbound Email actions 
Inbound email actions enable an administrator to define the actions ServiceNow takes when receiving email. Inbound email actions are similar to business rules, using both conditions and scripts. The inbound email action checks the email for a watermark that associates it with a task and checks for other conditions. If the conditions are met, the inbound email action runs the script.


By default, if an email has no identifiable watermark, an inbound email action attempts to create a new incident from the message. If the email has a watermark of an existing incident, an inbound email action updates the existing incident according to the action's script.


To add an Inbound Email Action:

Navigate to System Policy > Email > Inbound Actions
Click New
Complete the fields on the form

## Matching Inbound email to Inbound action type
![image](https://user-images.githubusercontent.com/12488769/148660388-617eb6fa-0f7b-4965-8caf-7df96f153440.png)













![image](https://user-images.githubusercontent.com/12488769/148660208-c70ac5ae-82c4-4086-88bf-10c4078e54b0.png)


## Reporting
https://github.com/bernicetempleman/SNOW-Reporting
## Notes
https://developer.servicenow.com/dev.do#!/guides/rome/now-platform/glossary/developer-glossary

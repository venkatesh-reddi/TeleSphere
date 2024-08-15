# TeleSphere
The TeleSphere is a Java-based application designed to manage customer details, track call records, and handle customer subscription plans. The system provides functionalities to store customer information, log call data, and manage customer subscription plans, making it an efficient solution for telecom service providers.

Features
Customer Management: Add, update, and remove customer details.
Call Tracking: Log and track call records associated with customers.
Plan Management: Manage various subscription plans, including plan details like charges, call rates, and data limits.
Billing System: Generate bills based on call records and the subscribed plan details.
Project Structure
The project is organized into the following packages:

com.telecom.customers: Handles customer-related operations.
com.telecom.calls: Manages call records.
com.telecom.plans: Manages subscription plans.
com.telecom.main: Contains the main application logic.
Classes
Customer
Represents a customer in the system.

Attributes: customerId, name, address, phoneNumber, email
Methods: Getters and setters, update customer information
CallRecord
Represents a call record.

Attributes: callId, customerId, callStartTime, callEndTime, callDuration, callType
Methods: Getters and setters, calculate call duration
Plan
Represents a subscription plan.

Attributes: planId, planName, monthlyCharge, callRatePerMinute, dataLimit
Methods: Getters and setters, modify plan details
Subscription
Represents the subscription of a customer to a plan.

Attributes: subscriptionId, customerId, planId, startDate, endDate
Methods: Getters and setters, check plan validity
TelecomManager
Controls the overall system operations.

Methods:
addCustomer(): Add a new customer.
removeCustomer(): Remove an existing customer.
addCallRecord(): Log a new call record.
assignPlanToCustomer(): Assign a plan to a customer.
generateBill(): Calculate the bill based on call records and plan details.
Database Structure
The system uses a relational database to store data. Below is the structure of the database:

Tables-

Customers
Stores customer details.

customerId	INT (Primary Key, Auto Increment)	Unique identifier for each customer.
name	VARCHAR(255)	Name of the customer.
address	VARCHAR(255)	Address of the customer.
phoneNumber	VARCHAR(15)	Contact number of the customer.
email	VARCHAR(255)	Email address of the customer.


CallRecords
Stores details of all calls made.-


callId	INT (Primary Key, Auto Increment)	Unique identifier for each call.
customerId	INT (Foreign Key)	ID of the customer who made the call.
callStartTime	DATETIME	Start time of the call.
callEndTime	DATETIME	End time of the call.
callDuration	INT	Duration of the call in seconds.
callType	ENUM('local', 'international')	Type of call.



Plans
Stores details of various subscription plans.--


planId	INT (Primary Key, Auto Increment)	Unique identifier for each plan.
planName	VARCHAR(255)	Name of the plan.
monthlyCharge	DECIMAL(10,2)	Monthly charge for the plan.
callRatePerMinute	DECIMAL(10,2)	Call rate per minute for the plan.
dataLimit	INT	Data limit in MBs for the plan.


Subscriptions
Links customers with their subscribed plans.--


subscriptionId	INT (Primary Key, Auto Increment)	Unique identifier for each subscription.
customerId	INT (Foreign Key)	ID of the customer who subscribed to the plan.
planId	INT (Foreign Key)	ID of the subscribed plan.
startDate	DATE	Start date of the subscription.
endDate	DATE	End date of the subscription.

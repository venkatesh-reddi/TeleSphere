
## Telecom Management System

### Overview

The  TeleSphere is a Java-based application designed to manage customer details, track call records, and handle customer subscription plans. The system provides functionalities to store customer information, log call data, and manage customer subscription plans, making it an efficient solution for telecom service providers.

### Classes and Features

#### 1. Customer
Represents a customer in the system.

- **Attributes**:
  - `customerId`: Unique identifier for each customer.
  - `name`: Name of the customer.
  - `address`: Address of the customer.
  - `phoneNumber`: Contact number of the customer.
  - `email`: Email address of the customer.
- **Methods**:
  - Getters and setters for each attribute.
  - Method to update customer information.

#### 2. CallRecord
Represents a call record.

- **Attributes**:
  - `callId`: Unique identifier for each call.
  - `customerId`: ID of the customer who made the call.
  - `callStartTime`: Start time of the call.
  - `callEndTime`: End time of the call.
  - `callDuration`: Duration of the call in seconds.
  - `callType`: Type of call (local or international).
- **Methods**:
  - Getters and setters for each attribute.
  - Method to calculate call duration.

#### 3. Plan
Represents a subscription plan.

- **Attributes**:
  - `planId`: Unique identifier for each plan.
  - `planName`: Name of the plan.
  - `monthlyCharge`: Monthly charge for the plan.
  - `callRatePerMinute`: Call rate per minute for the plan.
  - `dataLimit`: Data limit in MBs for the plan.
- **Methods**:
  - Getters and setters for each attribute.
  - Method to modify plan details.

#### 4. Subscription
Represents the subscription of a customer to a plan.

- **Attributes**:
  - `subscriptionId`: Unique identifier for each subscription.
  - `customerId`: ID of the customer who subscribed to the plan.
  - `planId`: ID of the subscribed plan.
  - `startDate`: Start date of the subscription.
  - `endDate`: End date of the subscription.
- **Methods**:
  - Getters and setters for each attribute.
  - Method to check plan validity.

#### 5. TelecomManager
Controls the overall system operations.

- **Methods**:
  - `addCustomer()`: Add a new customer.
  - `removeCustomer()`: Remove an existing customer.
  - `addCallRecord()`: Log a new call record.
  - `assignPlanToCustomer()`: Assign a plan to a customer.
  - `generateBill()`: Calculate the bill based on call records and plan details.

### Database Structure

The system uses a relational database to store data. Below is the structure of the database:

#### Tables

##### 1. Customers
This table stores customer details.

- **customerId**: INT (Primary Key, Auto Increment) - Unique identifier for each customer.
- **name**: VARCHAR(255) - Name of the customer.
- **address**: VARCHAR(255) - Address of the customer.
- **phoneNumber**: VARCHAR(15) - Contact number of the customer.
- **email**: VARCHAR(255) - Email address of the customer.

##### 2. CallRecords
This table stores details of all calls made.

- **callId**: INT (Primary Key, Auto Increment) - Unique identifier for each call.
- **customerId**: INT (Foreign Key) - ID of the customer who made the call.
- **callStartTime**: DATETIME - Start time of the call.
- **callEndTime**: DATETIME - End time of the call.
- **callDuration**: INT - Duration of the call in seconds.
- **callType**: ENUM('local', 'international') - Type of call (local or international).

##### 3. Plans
This table stores details of various subscription plans.

- **planId**: INT (Primary Key, Auto Increment) - Unique identifier for each plan.
- **planName**: VARCHAR(255) - Name of the plan.
- **monthlyCharge**: DECIMAL(10,2) - Monthly charge for the plan.
- **callRatePerMinute**: DECIMAL(10,2) - Call rate per minute for the plan.
- **dataLimit**: INT - Data limit in MBs for the plan.

##### 4. Subscriptions
This table links customers with their subscribed plans.

- **subscriptionId**: INT (Primary Key, Auto Increment) - Unique identifier for each subscription.
- **customerId**: INT (Foreign Key) - ID of the customer who subscribed to the plan.
- **planId**: INT (Foreign Key) - ID of the subscribed plan.
- **startDate**: DATE - Start date of the subscription.
- **endDate**: DATE - End date of the subscription.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgements
Thank you to the contributors and the open-source community for making this project possible.


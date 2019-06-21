## When a customer is created or updated, populate the credit risk evaluation from Dun and Bradstreet in the Unit4 Business World Customer record.

## Extension Flow Version
1.0

## Description

Use this flow to populate the Unit4 Business World Customer record with the credit risk evaluation provided by Dun & Bradstreet. 

## System requirements
- A flexifield group **CUSTRATING** has been defined and linked with the Customer:
    * **dbid_fx (write)** : Dun & Bradstreet identification of the customer
    * **update_rating_fx (read/write)**: indicates whether the credit risk must be updated
    * **d_b_rating_fx (read)**: the risk evaluation is stored in this field
    * **last_updated_fx (read)**: the date of an update is registered in this field
 
![broken image](/ExtensionsFlows/U4BusinessWorld/CheckCustomerCreditRisk/Images/CheckCreditRisk_1.JPG)
- An account on Dun and Bradstreet (https://developer.dnb.com/)
- The Dun and Bradsteet ID must be filled out in the dbid_fx field
- A Unit4 Business World account with access to Customers

## Authentication

Step 1 
- Required: a user and a password of a Dun and Bradstreet account

Step 2
- Type: basic
- Required: a Unit4 Business World user and a password





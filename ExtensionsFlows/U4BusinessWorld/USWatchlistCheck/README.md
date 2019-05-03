## When a customer is created or updated, check whether is present in the US Watch lists database.

## Extension Flow Version
1.0

## Description

Use this flow to automatically identify if the customer is present in the US Watchlist and Red Flags goverment database. 

## System requirements
- A flexifield group **CUSTCHECK** has been defined and linked to the Customer attribute:
    * **update_check_fx (read/write)**: indicates whether the watchlist information must be updated
    * **watchlist_fx (write)**: checkbox that indicates if the company is present in the Watchlist 
    * **last_updated_fx (read)**: the date of the updating is registered in this field
 
- Unit4 Business World account with access to Customers

## Authentication

Step3.
- Type: Basic
- Required: Unit4 Business World user and password





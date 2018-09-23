# Stock Notification API
## Goals & Functionality
* Create an API too monitor stock prices and send email notifications when conditions are met.
* Includes functionality for "noify me when",
	* MSFT drops below $100
	* MSFT increases above $100
	* At any point in last 3 moving months, drop of 10%
	* At any point in last 1 year, increase of 20%
	* TSLA drops > 8% in 1 day

## High Level Abstraction

| PATH  | Method  | Functionality |
|:-------------:|:---------------:|:-------------:|
| /check/\<*group_id*> | GET | Check all conditions for *group_id*. This is likely automated to run periodically. |
| /check/\<*group_id*> | POST | Set or Update the time to check conditions automatically |
| /check/\<*group_id*> | DELETE | Remove all history of *group_id* |
| /condition/\<*group_id*>  | GET  | List of all conditions for *group_id* |
| /condition/\<*group_id*> | POST  | Add a new condition for *group_id* |
| /condition/\<*group_id*>/\<*condition_id*> | DELETE | Remove condition for *condition_id* |

## Request Bodies

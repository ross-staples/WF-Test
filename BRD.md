# BRD - Release of Stop Payment
## BUSINESS REQUIREMENT DOCUMENT CONTENT (BRD) REVISIONS 
![image](https://github.com/user-attachments/assets/d1230add-fe0a-4b3e-b70c-fe81de712b6c)

### Process Flow Step	Detailed Steps
1. End user will start a workflow, via customer account or workflow queue, and enter the following details
  - **Account #:**
2.	The user will then receive a 2nd manual activity
  -Select Customer Requesting Release: *required*
  -	How was the Stop Payment Release Requested? *required*
    -	In-person at branch 
    -	Customer called in (Customer Care Only)
    -	Online Banking (Customer Care Only)
    -	Chat request (Customer Care Only)
    -	Email (Customer Care Only)
  -	Date Stop Payment was placed: *required*
  -	Check Number Start: 
  -	Amount of Stop Payment: 
  -	Is this item present on the accounts non-post? *If after 2:30pm please reach out to Deposit Services* Yes/No *required*
3.	WF will perform a stop payment search and pull back all stops that match the date Check Number Start and amount, if amount/Check # is input – up to 50 stop payments can be returned
4.	End user will be displayed all stops that match the criteria they entered, max of 50 stops returned, and they will have a drop down to select which stop payment, they want to release from Silverlake -
  -	Drop down to choose Stop Payment *required* Payee: | Date Placed: | Amount: | Check # Start: | Check # End: | Sequence # 
5.	If stop payment item is present on non-post? (stop payment will not be released from Silverlake) An email is sent to depositaccountservices@southside.com and WF will create a manual activity for Deposit Services
6.	Deposit Services MA:
  -	Review stop payment release info & Requestor Name
  - Continue with releasing stop payment? Yes/No 
  -	Comments:
7.	If item is not on non-post, or Deposit Services approves to remove the stop payment for a non-posted item, WF will release the specific Stop Payment from Silverlake using the sequence # for the Stop Payment that was selected by the end user
8.	If deposit account services choose to not release the stop payment, WF will leave the stop payment in Silverlake, and send an email to the originator letting them know the stop payment release was incomplete.
9.	WF will display a final manual activity for the user letting them know the stop payment was successfully released from Silverlake 
10.	An audit trail document will archive into Synergy – 
  -	Cabinet: Demand Deposit & Savings Cabinet
  - Type: Stop Payment – DDA & Stop Payment – SAV
  - Name: Release of Stop Payment Activity Report

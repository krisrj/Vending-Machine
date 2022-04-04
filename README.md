# Vending-Machine

Vending Machine Software
You’ve been asked to develop an application for the newest vending machine distributor, Umbrella Corp. They’ve released a new vending machine 
(Vendo-Matic 600) that is integrated with everyone’s bank accounts allowing customers to purchase products right from their computers for 
convenience sake. 
Menus and submenus: 
1. Display items 
2. Purchase items
 1) Feed Money
 2) Select Product
 3) Finish Transaction
3. Exit

5. Sales Report** Optional hidden menu item
Story Acceptance Criteria
As a vending machine owner, I need a way to 
update my vending machine with a standard 
amount of inventory every time it's started.

Given a file contains the list of items formatted correctly
When the vending machine is started

Then inventory is created/updated with what items are in each slot based on the contents of 
the file. Each inventory item has a name, price, and type (beverage, candy, chips, gum). 

Given an item is in the inventory file
When the vending machine is started and the inventory is updated
Then the slot indicated is filled with five of that product 

As a customer, I want to see items available for 
purchase in the vending machine. 

Given an item is available
When a customer displays items
Then the item is displayed with the name, slot identifier and purchase price

Given an item is sold out
When a customer displays items
Then the item is displayed as SOLD OUT

As a customer, I want to deposit money into the 
vending machine.

Given a customer is in the purchase menu
Then they are able to deposit money in whole dollar amounts

Given a customer is in the purchase menu
When they deposit money
Then his/her current balance is updated and displayed 

As a customer, I want to purchase items from the 
vending machine. 

Given a customer is on the purchase menu and has not deposited money (current balance is 
$0)

When they try to select a product
Then they are given an error message that they must deposit money before making a 
selection

Given a customer is on the purchase menu
When they select an item for purchase that is available
Then : 
1) the customer's current balance is updated based on item cost 
2) the inventory and 
balance of the vending machine are updated 
3) the item is dispensed and the user receives a 
message based on the item type: All chip items will print “Crunch Crunch, Yum!” All candy 
items will print “Munch Munch, Yum!” All drink items will print “Glug Glug, Yum!” All gum 
items will print “Chew Chew, Yum!” 
4) the customer is returned to the purchase menu

Given a customer is on the purchase menu 
When the customer attempts to purchase an item that is sold out or costs more than their 
current balance
Then they are given an error message and returned to the purchase menu

As a customer, I want my change to be returned 
when I'm finished purchasing items.

Given a customer is on the purchase menu
When they choose Finish Transaction
Then the customer recieves (a message with) their change using nickels, dimes and quarters 
using the smallest amount of coins possible and the current balance is updated to $0. 

They are 
then returned to the main menu.

As a vending machine owner, I want an audit file so 
that I can see what my vending machine has sold.

Given a customer has fed in money
When the audit file is viewed
Then there should be an entry for every time money was fed in labeled "FEED MONEY" that 
includes date, time, amount, new balance.

Given an item has been purchased 
When the audit file is viewed
Then there should be an entry for every purchase that includes date, time, item name, item 
slot, item price, remaining balance

Given a customer has completed a transaction
When the audit file is viewed
Then there should be an entry for every transaction completed labeled "GIVE CHANGE" that 
includes date, time, amount of change, remaining balance (should be $0)

As a vending machine owner, I want a sales report 
as a hidden menu option so that I can see the total 
sales since the machine was last started 

Given a product is in the vending machine
When the sales report is run
Then there is a line for that product with the item name | total number of sales

When the sales report is run
Then at the end of the report is a blank line followed by **TOTAL SALES** $dollar amount 
indicating the gross sales from the vending machine

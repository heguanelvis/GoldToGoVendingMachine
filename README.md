# GoldToGo Vending Machine
A command-line vending machine built with Java OOP fundamentals under Test-Driven Development approach.

## User Stories and Expectations for Vending Machine:
- *User Stories (MVP):* 
    - Vendor: 
        - As a vendor, I want to be able to build or update the inventory for the machine so that customers can get the items they want in most cases.
        - As a vendor, I want to be able to print audit file so that I can track the revenue and popular items.
    - Customer:
        - As a customer, I want to be able to purchase a certain item in the vending machine with certain cash values.
        - As a customer, I want to be able to get change or my money back if there is insufficient or unmatched funds.

- *Expectations for Vending Machine:*
    - Vending Machine should be able to store a inventory of items (reading the item store file).
    - Vending Machine should only store a certain quantity of items.
    - Vending Machine should assign each item a unique location.
    - Vending Machine should be able to display all items available to the customer.
    - Vending Machine should allow customer to select an item at a specific location.
    - Vending Machine should be able to update the number of a certain items in its inventory.
    - Vending Machine should be able to empty or refill the location where the item was stored.
    - Vending Machine should only accept certain cash values.
    - Vending Machine should be able to collect the cash given by a customer if it can give change to the customer.
    - Vending Machine should print the change amount given to the customer.   
    - Vending Machine should store the total amount of change and different change values.
    - Vending Machine should track the total amount of sales and revenue (writing to log file).
    - Vending Machine should be able to print the audit file (printing inventory and revenue).
    - Vending Machine should be able to handle such exceptions:
        - SoldOut Exception
        - StorageFull Exception
        - ChangeValue Exception
        - InsufficientPayment Exception

## Features
1. The vending machine dispenses beverages, candies, chips, and gums, and each vending machine item has a Name and a Price.

2. A main menu is displayed when the program runs presenting the following options:   
    >```
    >(1) Display Vending Machine Items
    >(2) Purchase
    >(3) Exit
    >```

3. Vending machine inventory is stocked via an input file when the vending machine is
started..

4. The vending machine is automatically restocked each time the application runs.

5. When the customer selects (1) Display Vending Machine Items, they are presented with a list of all items in the vending machine with its quantity remaining:
    * a. Each vending machine product has a slot identifier and a purchase price.
    * b. Each slot in the vending machine has enough room for 5 of that product.
    * c. Every product is initially stocked to the maximum amount.
    * d. SOLD OUT will be displayed when a product stock runs out.

6. When the customer selects (2) Purchase they are guided through the purchasing process menu:
    >```
    >(1) Feed Money
    >(2) Select Product
    >(3) Finish Transaction
    >
    > Current Money Provided: $1.00
    >```

7. The purchase process flow is as follows:
    * a. Selecting (1) Feed Money A customer can repeatedly feed money into the machine in valid whole dollar amounts (e.g. $1, $2, $5, $10).
        * i. The Current Money Provided indicates how much money the customer has fed into the machine.

    * b. Selecting (2) Select Product allows the customer to select a product to purchase.
        * i. Show the list of products available and allow the customer to enter to code to select an item.
        * ii. If the product code does not exist, the customer is informed and returned to the Purchase menu.
        * iii. If a product is sold out, the customer is informed and returned to the Purchase menu.
        * iv. If a valid product is selected it is dispensed to the customer.
        * v. Dispensing an item will print the item name, cost and the money
    remaining. Dispensing will also return a message:
            1>. All chip items will print “Crunch Crunch, Yum!”
            2>. All candy items will print “Munch Munch, Yum!”
            3>. All drink items will print “Glug Glug, Yum!”
            4>. All gum items will print “Chew Chew, Yum!”
        * vi. After the product is dispensed, the machine updates its balance accordingly and returns the customer to the Purchase menu.

    * c. Selecting (3) Finish Transaction allows the customer to complete the
    transaction and receive any remaining change back.
        * i. The customer’s money is returned using nickels, dimes, and quarters (using the smallest amount of coins possible).
        * ii. The machine’s current balance is updated to $0 remaining.
    
    * d. After the purchase is complete the user is returned to the “Main” menu to continue using the vending machine.

8. An audit file will be generated after each machine run to prevent theft.
    * a. Each purchase will generate a line in a file called log.txt
    * b. The audit entry is in the format:
        >```
        > 01/01/2016 12:00:00 PM FEED MONEY: $5.00 $5.00
         >01/01/2016 12:00:15 PM FEED MONEY: $5.00 $10.00
         >01/01/2016 12:00:20 PM Crunchie B4 $10.00 $8.50
         >01/01/2016 12:01:25 PM Cowtales B2 $8.50 $7.50
         >01/01/2016 12:01:35 PM GIVE CHANGE: $7.50 $0.00
         >```

9. A sales report function is provided through a hidden menu option:
    * a. On the main menu, hitting option (“4”) is allowed, which writes to a sales report that show the total sales since the machine was first in use. The name of the file is unique and based on the specific timestamp.
    * b. The format is as follows:
        >```
        >Potato Crisps|10
        >Stackers|3
        >Grain Waves|0
        >Cloud Popcorn|50
        >Moonpie|23
        >Cowtales|2
        >Wonka Bar|1
        >Crunchie|3
        >Skor|4
        >Cola|8
        >Dr. Salt|9
        >Mountain Melter|12
        >Heavy|11
        >Diet Cola|6
        >U-Chews|4
        >Little League Chew|2
        >Chiclets|0
        >Triplemint|0

        >Total Sales: $10.00
        >```

## Vending Machine Data File Instructions
The input file that stocks the vending machine products is a pipe | delimited file. Each line is a separate product in the file and follows the below format. Please update the vending machine stocks according to this format.

| Column Name   | Description |
----------------|-------------|
| Slot Location | The slot location in the vending machine where the product is set. |
| Product Name  | The display name of the vending machine product.                   |
| Price         | The purchase price for the product.                                |
| Type          | The product type for this row.                                     |




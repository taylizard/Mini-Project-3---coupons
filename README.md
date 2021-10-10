# Mini-Project-3---coupons
In this mini project, you are asked to process two different types of coupons and determine how they may or may not affect the total of purchases. 

The starter project contains multiple files. 

The Date Class
The “Date.h” file has defined a Date class and its related member and friend functions. Do not modify this file. It contains only one object-level data member, days_, that stores the number of days that have passed since the beginning of the year. That is, 0 refers to January 1, 1 refers to January 2, and so on. The default constructor has been implemented to set the days_ data member to 0. 
You are to first implement the above overloaded operators in the “Date.cpp” file. It’s highly recommended that you implement and test these operators before working on the rest of the project.

This function is to set the days_ data member according to the str parameter. You may assume that str will take the format of “MM/DD” and represent a valid date.

This function is to support the comparison between two Date objects and return true if the Date object on the left is earlier than the Date object on the right. 
For example, given the following Date objects:
Date pi_day , april_fool, independence_day ;
pi_day = "03/14";
april_fool= "04/01"
independence_day = "07/04"
The overloaded function shall return true for the following comparisons:
pi_day < april_fool		april_fool < independence_day 		
It shall return false for the following comparisons:
april_fool < pi_day		april_fool < april_fool 	

This function is to display the date object in “MM/DD” format.

The Coupon Class
The “Coupon.h” file defines the base class Coupon. It holds one data member expiration_, representing the expiration date of a coupon. It is under protected access so that it can be accessed directly by member and friend functions of the derived classes. Do not modify this file.

You are to implement the two member functions in the “Coupon.cpp” file. It’s highly recommended that you implement and test these functions before working on the rest of the project.

This function is to create a Coupon object by setting the expiration date according to the str parameter. You may assume that str will take the format of “MM/DD”.

This function is to return true if the expiration date is before the str parameter, false otherwise. Again, you may assume that str will take the format of “MM/DD”.

These two functions have been implemented for you. They are to be overridden later by the derived classes. Do not change these two functions.

The DeductionCoupon Class
The “DeductionCoupon.h” file defines a derived class of Coupon. It adds two new data members, representing the amount of deduction and the minimum purchase price before the deduction can be applied. Do not modify this file.


It is designed to handle coupons like the following. The first image shows a deduction coupon where the $50 deduction can only be applied when a purchase is at least $500. The second image shows a deduction coupon where the $20 deduction can only be applied when a purchase is at least $100.


You are to implement the member functions in the “DeductionCoupon.cpp” file. It’s highly recommended that you implement and test these functions before processing the transactions file.

This constructor is to create a new DeductionCoupon object using the parameters provided. You are required to invoke the base class constructor to set the expiration date. Again, you may assume that str will take the format of “MM/DD” and represent a valid date in a non-leap year. 

This function overrides the calculateCost method in the base class. It takes one parameter as the purchase total and returns the cost after deduction is applied if the purchase total meets the minimum purchase requirement for the coupon. Otherwise, the function returns the purchase total without deduction. 

This function overrides the toString method in the base class. It returns a string including information about the invoking DeductionCoupon object. It must include the expiration date, the deduction amount, and the minimum purchase requirement. Below please find an example display of a DeductionCoupon object. For example, “$5 OFF ABOVE $25, Expired on 03/31” or “Expiration date: 11/01, $50 OFF purchase of $500 or more”.

The PercentageCoupon Class
The “PercentageCoupon.h” file defines another derived class of Coupon. It adds one new data member, representing the discount percentage of a coupon. Do not modify this file.

It is designed to handle coupons like the following. 

You are to implement the member functions in the “PercentageCoupon.cpp” file. It’s highly recommended that you implement and test these functions before processing the transactions file.

This constructor is to create a new PercentageCoupon object using the parameters provided. You are required to invoke the base class constructor to set the expiration date. Again, you may assume that str will take the format of “MM/DD” and represent a valid date in a non-leap year. 

This function overrides the calculateCost method in the base class. It takes one parameter as the purchase total and returns the cost after percentage deduction is applied. 

This function overrides the toString method in the base class. It returns a string including information about the invoking DeductionCoupon object. It must include the expiration date, the deduction amount, and the minimum purchase requirement. Below please find an example display of a PercentageCoupon object. For example, “15% OFF, Expired on 03/31” or “Expiration date: 11/01, 25% OFF”.
Processing the transactions file
Now that you have completed all of the classes we need for this project, you are ready to process the “transactions.txt” file. The first line of the file contains a date representing the date of all purchases in the file. Each line afterwards represents one purchase and coupon presented. 
The first item in each line is the total purchase amount.
The second item explains the type of coupon presented.
The third item represents the expiration date of the coupon.
For a deduction coupon, the fourth item represents the deduction amount and the fifth item represents the minimum purchase required for the deduction to be applied.
For a percentage coupon, the fourth item represents the percentage of discount. There is no fifth item.
The main function must create appropriate PercentageCoupon and DeductionCoupon objects to evaluate whether a coupon has expired and what the final cost would be for each transaction. The following is a sample output showing the result of processing the transactions in the “transactions.txt” file.
Since the file sets 10/15 as the date of all purchases, the coupons in the first, third, and fifth transactions have expired and the final cost remains unchanged from the total.
Although the coupon in the fourth transaction is still in effect, the purchase is below the minimum purchase required for the coupon. As a result, the final cost remains unchanged from the total.
For the other transactions, the final costs reflect the application of the respective coupon. 

Disclaimer: You may update the “transactions.txt” file to match your testing interest and purpose as long as you use the exact same transaction types and follow structure guidelines provided above. We reserve the right to modify the content of the transactions when testing your project.

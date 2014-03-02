Two-Roads-Algorithmic-Challenge
===============================

This is a challenge motivated by applications in market book building. Assuming the data-provider provides updates to the market-book in a certain format, you need to design an efficient data structure and implement update and access operations as specified in the data set. For simplicity we have only provided one side of the market book. A  correct solution to this question should be a good starting point. We have provided some hints but we are hoping to be vowed by more efficient algorithmic solutions to the problem at hand.


[ Instruction Files ] 
Please email solutions to data-science-challenge (AT) tworoads (dot) co (dot) in with a short-name like "mithrandir".

Detailed Description: 
You need to implement the functions of my_class.hpp, such that it implements a correct and efficient market book. You are not expected to make any changes in any other existing class. As with any other solution, correctness trumps efficiency. To assist in checking correctness of implementation, we have provided sample lookup values in the file Log.txt. Once you are satisfied with correctness, please try to look at the pattern of update and access operations to optimize your implementation to minimize the time taken.

Data: 
The data consists of tuples of (double price, unsigned int size) 
All sizes are strictly greater than 0 (0 will be interpreted as an invalid value) 
All prices are integral multiples of 0.25 and are strictly positive.
A tuple (price_a, size_a) is considered higher than (price_b, size_b) if price_a > price_b. 
By construction, we will not have two tuples with the same price in our data structure. 

The following operations are broadly what need to be supported: 
To update the book the data-provider might indicate that the new size at price price_a is size_a 
void InsertOrUpdate ( double price_a, unsigned int size_a )

void Delete ( double price_a )
is used to convey that all orders have been canceled at the specified price. 

bool Lookup ( unsigned int level, double& price, unsigned int& size)
The lookup call should return true and set the price and size variables to the values of the levelth highest tuple. If such a level does not exist, then the invalid values (0 for price and size) should be set. The highest tuple has level = 1 ( i.e. levels start from 1 .)
Further details are in the my_class.hpp file. 

What is provided:
In the [ Instruction files ] you are provided the following files:
Input.txt contains the test sequence of InsertOrUpdate, Delete and Lookup operations.
my_class.hpp defines the functions that you need to complete the implementation of.
main.cpp, utils.hpp are helper classes which are needed to test your solution. The compiled exec will log the values returned by lookup calls at the specified sampling rate, alongwith the total CPU Cycle count used in the data structure operations. 
Log.txt contains values for selected LookUp calls in sample data. This has been provided to check correctness of implementation. Log.txt contains sample results.
Hints to improve efficiency: 
Keep in mind that the data and access patterns are not random. 
Prices are localized, dense and structured.
New insertions/deletions are relatively infrequent compared to updates or Lookups.
At any point of time there aren’t too many active tuples.
Lookup and delete operations are mainly/exclusively at higher levels only.
You should look at exploiting these features of the data. Think about specific data structures/caching etc.

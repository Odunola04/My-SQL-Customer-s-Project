# My-SQL-Customer-Data 
Repository Name: Subscription Analytics
Create DATABASE Subscription_DB

Select * from [dbo].[LITA Capstone CS]

-----Retrieve the total number of customers from each region----
Select region, COUNT(distinct customerID) as total_customers from [dbo].[LITA Capstone CS]
Group by Region;

-----Find the most popular Subscription------
Select top 1 SubscriptionType, COUNT (Distinct customerID) As number_of_subscribers
from [dbo].[LITA Capstone CS]
Group by SubscriptionType
Order by total_customers desc; 

-----Find customers who cancelled their sub within 6 months----
Select(CustomerID,
CustomerName, 
SubscriptionType,
SubscriptionStart, 
SubscriptionEnd
datediff(Month, Subscriptionstart,subscriptionend) as subscription_duration From [dbo].[LITA Capstone CS]
where canceled = 1 AND Datediff(month
join subscription ON customerID = customerID where subscriptionEnd is not null
datediff subscriptionEnd, Subscriptionstart)<=183;
Group by Month

------Calculate the average subscription duration for all customers------
Select avg(datediff(day, subscriptionstart, subscriptionend)) as avg_subscription_duration
From [dbo].[LITA Capstone CS]

-----find customers with subscription longer than 12 months
Select customerid
From [dbo].[LITA Capstone CS]
Where datediff(month, subscriptionstart  subscriptionend) > 12;

----calculate total revenue by subscription type----
 Select subscriptiontype,
Sum(revenue) as total_revenue 
From[dbo].[LITA Capstone CS]
Group by subscriptiontype;

----find the top 3 regions by subscription cancellation------
Select top 3 region,
Count(*) as subscriptionend_count
From [dbo].[LITA Capstone CS]
Where subscriptionend is null
Group by region
Order by subscriptionend_count desc;


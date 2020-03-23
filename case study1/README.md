## Case study 1.

Problem statement:
**determine if the usage patterns for users differ between different devices.**

For example, do users using Samsung devices use more call minutes than those using LG devices?

My solution :

We have provided three datasets as follows 
1)*User_usage*  with columns 
* outgoing_mins_per_month
* outgoing_sms_per_month
* monthly_mb
* use_id

2)*User_device* with columns
* use_id
* user_id
* platform
* platform_version
* device
* use_type_id

3)*Devices* with columns
* manufacturer
* Marketing Name
* Device
* Model

I form a single dataframe with columns for user usage figures(calls per month, sms per month etc)
and also columns with device information (model, manufacturer, etc). 
Then merge sample datasets together into one single datasets for asalysis.


Another solution:
we could write for loops for this task.
The first would loop through the use_id in the user_usage dataset, and then find the right element in user_devices.
The second for loop will repeat this process for the devices.

However, using for loops will be much slower and more verbose than using Pandas merge functionality. 
So,  if you come across this situation – don’t use for loops.


Steps : 

1.Add the platform and device to the user usage - use a left join.
2.Now, based on the "device" column in result, match the "Model" column in devices and merge them.

Final merged result with device manufacturer information merged onto the user usage table. Two left merges were used to get to this point.

3.Use data aggregation technique to get final result. 





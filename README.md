# Project-1  Age & Gender Relationships
#This is a brief overview of the relationships of age and gender to car crash data.
#The data was pulled from the City of Chicago Data Portal at https://data.cityofchicago.org/ ,
#and focuses on the most recent complete year, 2022. 
#For this exercise, I merged vehicle and driver CSV files from the City of Chicago Data Portal, and cleaned them with the following actions:
Removing rows for gender with unknown variables to reduce it to a binary value. The data provided on the portal was more akin to NaN or unknown values, rather than any specific non-binary association.
#I also removed outliers from the age data, where the data most likely represented input errors again, such as negative age values (-47) or values too high to be plausible (130).
#Data was also limited to the previous five years, as this allowed a small enough dataset to manipulate, while mitigating PC errors associated with low memory.



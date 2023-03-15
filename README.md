# covid-analysis


Complete architecture to follow:


![image](https://user-images.githubusercontent.com/66850958/225465509-451cd303-15e2-444d-b1e2-614e3aa2a62e.png)


Dataset Used

This AWS dataset contains statistics (CSV and JSON files) of daily covid 19 dataa cross multiregions in US. It includes total confirmed cases, cases at US state level
cases at US county level. It has total daily tests conducted at state and county level with hospital names and number of beds utilized.


https://dj2taa9i652rf.cloudfront.net/

Step1: Create S3 buckets and store data in them.



![image](https://user-images.githubusercontent.com/66850958/225465407-3fa31333-0be0-4d44-a598-b43c474fd21e.png)



Step2: Create glue crawlers to get the metadata of files.



![image](https://user-images.githubusercontent.com/66850958/225465601-afea4501-f97f-42be-b521-94e698e49f8a.png)


Step3: Analysing the AwsDatacatalog Tables using Athena.


![image](https://user-images.githubusercontent.com/66850958/225465910-74d51446-454f-49af-98c3-8ef68833d407.png)


Step4: Creating jupyter notebook to interact with athena data and store it in dataframes for transformation. 

See the code in aws-athena-trans.ipynb file

Step5: build the retional model using python and store the 3 Dim table and 1 fact table in S3.


![image](https://user-images.githubusercontent.com/66850958/225466818-834b4a37-9d58-4265-9539-7ece6d1d383a.png)



Step6: Build a Etl job in glue to connect to redshift and copy the transformed files from S3 using the copy command.



![image](https://user-images.githubusercontent.com/66850958/225467053-b89fa3e3-2a58-406d-b8bd-b68f3eff6c6b.png)


#####################################END##################################################









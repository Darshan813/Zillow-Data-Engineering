#Zillow End to End Data Engineering Project


![DE pipeline image](https://github.com/Darshan813/Zillow-Data-Engineering/assets/79681552/e870a27b-e44d-44ca-bfc9-8304e7ce114a)  
  
  
  


-> The Project Extract the data using the Zillow Rapid Api.  
-> After the data is Extracted the file is stored in the AWS EC2 Server.  
-> The file is than transfer to the AWS S3 bucket using Airflow, this bucket stores all the original data.   
-> After this step, the Lambda function transfers the file from the main S3 bucket to the copy of the S3 bucket, this bucket data will be used for further transformation.   
-> When the file is transfered to the copy_data bucket, another lambda function is triggered and this lambda function contains the transformdata code, which further transform the data and store it in the new S3 bucket in the csv format.  
-> If this process is success, the Airflow will run the s3 keysensor task where it will check whether the transform file is in the transformdata bucket, if it is present it will load the data into the Redshift datawarehouse.  
-> After loading the data into the redshift, we will then connect the quicksight for further analysis and visualization.  
  
Here are some visualizations, I have made.  

![visualize1](https://github.com/Darshan813/Zillow-Data-Engineering/assets/79681552/a1056222-4100-4d9a-9749-fb471a3e7f13)   

  


![visualize2](https://github.com/Darshan813/Zillow-Data-Engineering/assets/79681552/17bd5622-a182-4114-8d2e-1fa4b0c14506)  

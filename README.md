### task_railofy
> Applying DVC to the Huge stock market Kaggle Dataset.
> https://www.kaggle.com/borismarjanovic/price-volume-data-for-all-us-stocks-etfs

#### Process: 
* Downloading the kaggle dataset on your local machine. (Also we can use dvc get command to get the data from the web if you have hosted it somewhere on github or any other place)
* Then initializing the git and DVC in that particular folder.
* Adding the data to DVC. Using **dvc add (location of the data folder in which the data is  stored.)**
* Then we will run **git add** command and add the generated file, which was generated in our directory when we ran the command **dvc add (location of data)**, and also the **.gitignore** file.
* Then we will commit the changes.
* Now we want to move our data to a remote storage, in our case it is my persoal google drive. So I will create one folder in my google drive take the location of the folder and then add that location as remote location to our dvc file, by that dvc will know the remote location of our data. the command to that is as follows:
    > dvc remote add -d storage gdrive://(location of the drive)
 
    > git commit .dvc/config -m "Configuring the remote storage" #commiting the changes


    > dvc push #pushing the data from local to the remmote storage.
* Now if we will check our drive then the data will appear. Link to the drive: 
   >  https://drive.google.com/drive/folders/1385eoDIMKKbJ5e3gH8d4ERA7OnxrlmVx?usp=sharing
*  Suppose we have a large dataset i.e. more than 2 gb, so we can still publish it on our git repository through the **data.dvc** file. So this **data.dvc** file will containe the location of our DVC repository and if the user will run the **dvc pull** command then it can download the new copy of the data on that user's local storage, with just one command.
*  Using DVC we can make our large data more viable.

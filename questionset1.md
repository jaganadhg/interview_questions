1)  Demonstrate the use of lambda functions to solve the follwing use case.
input_list = [1,2,3,4,5,6,7,8,9,10] 
output = [1,3,5,7,9]
Hint -> use filter (lambda )

2) Examine the follwing code and demonstrate how to access the **kwargs and validate the inputs.

class MyDataFilter:
    """Filter Data""
    
    def __init__(sefl):
        self.filterd_data = list()
    
    def filter(self, data_set : list, **filter_params : str):
        """Filter a list by conditions. The conditions can be none,
        oddd or even. return the filtered the results by the
        condition
        :params data_set: List of values
        :params filter_params: filter paramater
        :returns filterd_data: returns the filter data as list"""
        
        return self.filterd_data
  
 3) As part of the project we need to connect to rest API service. The API rnd point details and input is available at
 
    https://developer.github.com/v3/repos/comments/#create-a-commit-comment .
    The base URL for the API is - https://api.github.com/
    
    Demonstrate the use of REST API libraries to perfrom the operation
    
 4) There are two machines Machine_A and Machine_B  identified with hostnames hostmaster and hostsalve. 
 The requorment is to establish as connection from hostmaster to hostsalve thorugh python. 
 A specified user name and password will be provided. Once the connection is established excute "ls -la" command 
 capture the results ans store it in a string for analysis.
 
 5) Write a reguler expression based sution for the following problem
 Input - 
 data = ["/mnt/volume1/vol/img.img","/mnt/volume1/some.img","/mnt/volume2/simg.img"]
 pattern = "volume1"
 
 result = {"volume1" : 2}
 
 6) Create 5 files with one or two sentences in it. Store the files in a folder. 
 read each files and count the words. Write the word cout of each file to a new file.
 
 Input Folder/
  - file1.txt
  - file2.txt
  - file3.txt
  - file4.txt
 
 Output Structure
 file1.txt
 word1 : 10
 word2 : 5
 
 ....
 
 file2.txt
 word1 : 2
 word2 : 5
 
 7) Copy paste the XMl data from the URL to a file books.xml 
 https://docs.microsoft.com/en-us/previous-versions/windows/desktop/ms762271(v%3Dvs.85)
 Write a program to access the author name and title.
 
 

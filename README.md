# .NET Project
## Project Introduction
>Our project is dedicated to helping teachers in hebut create an educational administration program(Call this application for short)for them to manage students and classes,and our program is displayed by web interface.
## Project function
>①`The teachers are able to create students and classes in the application and to ass students to
classes.`  
>②`The teachers are able to modify the classes and the students.`  
>③`The teachers are able to delete a student or a class.`  
>④`The teacher are able to add or remove students from classes.`  
## Installation Environment
>①`Install visual studio 2019`,the download address is:https://visualstudio.microsoft.com/zh-hans/vs/  
>②Use the system's own decompression software or third-party decompression software similar to band zip to `unzip the package containing the program we uploaded.`

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/2.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/3.png)

>①`Open EF_ WEB.sln file in vs2019`  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/4.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/5.png) 

## Program Composition  
#### Frame Composition  
>①`ControllerLayer`  
>②`ModelLayer`  
>③`DataAccess` 
#### Database Framework  
>`Entity Framework`

## Use steps
### Warning
>`Note that webform1.aspx is used to test and debug all functions, please do not run it, otherwise it will be used to cover the existing database data.`  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/6.png)  

### Function Realization  
#### Add and Delete student
>①`Run the 'default.aspx' file`,all the following functions are implemented on the basis of executing this file.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/7.png)  

>②`Enter the name of the added student number and click Add`,and you can see the student is be added.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/8.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/9.png)  

>③`Click Delete`,and you can see the student is be deleted.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/10.png)  

#### Update the student
>①`Input the student number of a student in the database, input the corrected name, and click Update`,you can see the student is updated.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/11.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/12.png)  

#### Select the student
>①`Enter the student number of a student in the database and click Select`,you can see the selected student.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/13.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/14.png)  

#### Add class and Delete class
>①`Enter the name of the added class number and click Add`,and you can see the class is be added.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/15.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/16.png)  

>③`Click Delete`,and you can see the class is be deleted.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/17.png)  

#### Update the class
>①`Input the class number of a class in the database, input the corrected name, and click Update`,you can see the class is updated.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/18.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/19.png)  

#### Select the class
>①`Enter the class number of a class in the database and click Select`,you can see the selected class.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/20.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/21.png)  

#### Add student to the class and Delete student from the class
>①`Input the existing student number and class number in the database and click Add`,and you can see the student is added to the class you input.  

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/22.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/23.png)  

>②`Click Delete`,and you can see the student is deleted from the class.

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/24.png)  

#### Select all information of a student according to the student number
>①`Input the student's number,and click the select`,and you can see all the student's information.

>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/25.png)  
>![image](https://github.com/MrEra0116/EF_WEB/blob/main/images/26.png)  



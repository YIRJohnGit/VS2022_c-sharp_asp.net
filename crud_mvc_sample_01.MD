# Entity Framework Core and CRUD Operations with MVC in Visual Studio 2022

### Step 1 - Create A New Project
```
	Create New Project with ASP.NET Core Web App (Model-View-Controller)
		Project Name < EFMVC >
		Location < J:\VS2022>
		Solution Name < EFMVC >
		Click on < Next >	
			Framework < .NET 6.0 (Long Term Support) >
			Authentication Type < None >
			Uncheck < Configure for HTTPS >
			Uncheck < Enable Docker >
			Click on < Create >
```

### Step 2 - Installing Missed Packages
```
Go to Solution Explorer and right Click on the < Project > Folder
		Click an Select < Manage NuGet Packages >
			Search < ef.core > Select < Microsoft.EntityFrameworkCore >, Select and Click <Install>
			Search < ef.core.tool > Select < Microsoft.EntityFrameworkCore.Tools >, Select and Click <Install>
			Search < ef.core.sql > Select < Microsoft.EntityFrameworkCore.SqlServer >, Select and Click <Install>
```
![image](https://user-images.githubusercontent.com/111234771/199981717-24f34991-5306-4361-af2b-f59860622806.png)

![image](https://user-images.githubusercontent.com/111234771/199981804-a82eed1a-84f3-42b2-9f0b-941df51b4fb3.png)

![image](https://user-images.githubusercontent.com/111234771/199981871-2169b11f-4abc-49e0-b164-4024b099f04c.png)


### Step 3 - Create A New Models
```
  Go to Solution Explorer and right Click on the < Models > Folder
	Select < Add >, in Sub Menu < Class > Teacher.cs
```
***...for Creating 2 Models  Teache.cs and Subject.cs***

_in Teacher.cs_
```
        public int TeacherId { get; set; }
        public string TeacherName { get; set; }
        public string TeacherAddress { get; set; }
        public int TeacherAge { get; set; }
```
_Teacher.cs File_
![image](https://user-images.githubusercontent.com/111234771/199998410-070804c8-b104-4a2d-a987-208db9ef883f.png)

_in Subject.cs_	
```
        public int SubjectId { get; set; }
        public string? SubjectName { get; set; }
        public string SubjectTerm { get; set; }
        public int SubjectCredets { get; set; }
```
_Subject.cs File_
![image](https://user-images.githubusercontent.com/111234771/199998101-37479b95-12fe-403c-819d-050237862b1c.png)


### Step 4 - Designing a Context
_Context can be used as Special Class and maintain Session Between Database and Applications_
```
Go to Sollution Folder and Right Click on Add Folder from the Dropdown Menu
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/199987130-bab57bf6-e33b-44b5-813b-60754659a03d.png)
```
Go to Side the Context Folde, Right Click and add a Class File MVCContext.cs 
```
```
using EFMVC.Models;
using Microsoft.EntityFrameworkCore;

namespace EFMVC.Context
{
    // Step1
    public class MVCContext: DbContext
    {
        // Step 2 - Adding Constructor
        public MVCContext(DbContextOptions options):base(options)
        {
            #pragma warning disable 
        }

        // Step 3 - Adding Constructor
        public DbSet<Subject> Subjects { get; set; }
        public DbSet<Teacher> Teachers{ get; set; }
    }
}
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/199991234-f72c15d7-27fb-4f22-9572-edea8dd5453d.png)


### Step 5 - Register Context in the Dependency Injuction Container

_Add the Connecting String_
![image](https://user-images.githubusercontent.com/111234771/199996497-5f502252-ff98-4d99-8f34-460f098dcd2d.png)

_Go to Program.cs in the root directory and register_
![image](https://user-images.githubusercontent.com/111234771/199997206-807f8ac0-2573-4ae2-89fa-39c96dda36dd.png)


***...for Migration Creating a table
```
add-migration Independent 
```

***... Adding Entity Subject Can Have Many Teachers***
![image](https://user-images.githubusercontent.com/111234771/199999488-0632b5c2-42e3-4514-9de9-c240b8b43dd1.png)

***... Adding Entity Teacher Can Have Many Subject*** 
![image](https://user-images.githubusercontent.com/111234771/199999739-9eaadc78-1d04-4ab8-aabd-4f39c5f9d6c9.png)


***...for Migration Creating a table Many to Many***
```
add-migration ManyToMany
update-database
```

***... Adding Entity Teacher Can Have Only One Subject*** 
![image](https://user-images.githubusercontent.com/111234771/200030150-a8ea3c43-f640-43f6-859a-8f1358421bec.png)

***... Adding Entity Subject Can Have Many Teacher*** 
![image](https://user-images.githubusercontent.com/111234771/200030210-4fe99624-e17f-42d0-9129-7bae665dfb7b.png)


***...for Migration Creating a table One to Many***
```
add-migration ManyToOne
update-database
```

### Step 6 - CRUD Operations
***...For adding connecting String***

_Result Sample View_
![image](https://user-images.githubusercontent.com/111234771/200054108-acf58dde-6373-4723-9b7a-29cf3770f832.png)

***...For Binding the Connecting String with Service***

_Result Sample View_
![image](https://user-images.githubusercontent.com/111234771/200054185-ba9d00b4-b1c3-4934-a638-8b1947beae4f.png)



# Need to re learn 
https://youtu.be/Ep0sFH-2nMQ

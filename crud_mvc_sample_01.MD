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
	Select < Add >, in Sub Menu < Class >
```
```
	-> teacher.cs
  
		public int TeacherId { get; set; }
		public int TeacherName { get; set; }
		public int TeacherAddress { get; set; }
		public int TeacherAge { get; set; }
```
-> subject.cs	
		public int SubjectId { get; set; }
		public int SubjectName { get; set; }
		public int SubjectTerm { get; set; }
		public int SubjectCredets { get; set; }


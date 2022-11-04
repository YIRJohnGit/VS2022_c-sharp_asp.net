# ASP.NET Entity Framwork with VS2022

### Step 1 - Create a New Project (Web App / Empty) ###
```
	Select < ASP.NET Core WebApp >
		Click On Next
		Specify the Project detail and framework
			Project Name < SimplilearnEF >
			Location < J:\VS2022 >
			Solution Name < SimplilearnEF >
			Framework < .NETFramework 4.7.2 >
			Click on Create
				Select < Empty > New ASP.NET Web Application
				Create The Project 
```

### Step 2 - Adding Entityframe work to the project ###
```
Go to Solution Explorer
	Right Click an Select < Manage NuGet Packages >
		Go to Browse, Search and Select < Entityframework > with 5.0.0 Version
		Click on Install
		Click on Agreeemnt Terms

```
_Result_

![image](https://user-images.githubusercontent.com/111234771/199929315-7249195b-80eb-466e-8435-0db6e7825452.png)

### Step 3 - Connecting to a Database ###
```
Go to Add Connection 
	Data Source < Microsoft SQL Server ( SqlClient) >
	Server Name < (LocalDB)\MSSQLLocalDB >
	Enter Database Name < SimplilearEFDB >
	Click on < Ok > Button
	Confirm the Create / Overwrite
```
![image](https://user-images.githubusercontent.com/111234771/199949304-7e1e0482-5857-40be-901b-3f00000d4c8e.png)

```
Go to Server Explorer to Verify, Create and Insert Data, 
	Select The Table and Create SQL Query
		Create table Departments
		(
			ID int primary key identity,
			Name nvarchar(50),
			Location nvarchar(50),
		)

		Create table Student
		(
			ID int primary key identity,
			FirstName nvarchar(50),
			LastName nvarchar(50),
			Gender nvarchar(50),
			Fees int,
			DepartmentId int foreign key references Departments(Id)
		)

		Insert into Department values ('Engineering','Block B')
		Insert into Department values ('Law','Block C')
		Insert into Department values ('Commerce','Block A')

		Insert into Student values ('Elan','Cross', Male, 250000, 1)
		Insert into Student values ('Rick','Rollins', Male, 120000, 3)
		Insert into Student values ('Karl','Dennings', Male, 250000, 1)
		Insert into Student values ('Drew','Cosby', Male, 300000, 2)
		Insert into Student values ('Halen','Keller', Female, 300000, 2)
```
_Result_

![image](https://user-images.githubusercontent.com/111234771/199949739-b1969745-29aa-43b9-b9bd-7d69d3d7a49d.png)


### Step 4 - Create New Entity Data Item (ADO.NET Entity Data Model) ###
```
Go to Solution Explorer, Right Click and Select Add New Item
		Go to < Data > Tree, Select < ADO.NET Entity Dta Modal >
		Name < StudentModel >, Click on Add
		Select the Model COntaines < EF Designer From Database >, Click on Next
		Select Created Databases or Create a New Connection....
		Save Connection Settings < StudentDBContext > (SimplilearnEFDBEntities). Click on Next
		Select The Entity Version, Click on Next
		Select the tables (Departments, Student), 
		Model Namespace < StudentModel > Click on Finish
```

### Step 5 - Create A web Form ###
```
	Go to Solution Explorer, Right Click and Select Add New Item
		Go to < Web > Tree, Select < Web Form >
		Click on Default Name and Finish
		Go to Inside HTML Div Tag
		(Open the a Tool Box from View Menu)
			Search and Select < GridView >
			Search and Select < EntityDataSource >
			Go to < Build > Menu and Select < Build >
			Go to < Design > Pattern Tab
```
```			
				Right Click on the < Entity Data Source > 
					Select < Show Smart Tag >
						Configure Data Source 
							Named Connection < StudentDBContext >
							Default Container Name < StudentDBContext >, Click on Next
							Select EntitySetName < Departments >, Click on Finish Button
```
```
				Right Click on the < Grid View Tasks >
					Select < Auto Format ..... >, to Change the Format of the Table
					Select < Choose Data Source > < EntityDataSource1 >
					Select < Edit Columns.... >
						 Select TemplateField, Click on Add
						 	HeaderText : Students, Click on < Ok >
					Select < Edit Template... >
						Add Grid View from Toolbox, (Drag and Drop Inside Template)
							Click on Edit < DataBinding ... >
								Go to DataSource, Select Custom Binding, Code Expression  < Eval("Students")>, Click on Okay
```
```
				Right Click on the < Grid View >
					Click on the < End Template Editing >
				Right Click on the < Entity DataSource >, Go to Properties
					Include < Students >
```
### Run the App ###
	IIS Express


_Reference Link_
https://youtu.be/rWy-s_yf664

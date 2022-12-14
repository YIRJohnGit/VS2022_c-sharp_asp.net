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
_Result_
![image](https://user-images.githubusercontent.com/111234771/199956920-7bdb4d19-069e-4e5e-ac09-6e0ec78c06fc.png)

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

		Insert into Departments values ('Engineering','Block B')
		Insert into Departments values ('Law','Block C')
		Insert into Departments values ('Commerce','Block A')

		Insert into Student values ('Elan','Cross', 'Male', 250000, 1)
		Insert into Student values ('Rick','Rollins', 'Male', 120000, 3)
		Insert into Student values ('Karl','Dennings', 'Male', 250000, 1)
		Insert into Student values ('Drew','Cosby', 'Male', 300000, 2)
		Insert into Student values ('Halen','Keller', 'Female', 300000, 2)
```
_Result_

![image](https://user-images.githubusercontent.com/111234771/199949739-b1969745-29aa-43b9-b9bd-7d69d3d7a49d.png)


### Step 4 - Create New Entity Data Item (ADO.NET Entity Data Model) ###
```
Go to Solution Explorer, Right Click and Select Add New Item
	Go to < Data > Tree, Select < ADO.NET Entity Dta Modal >
	Name < StudentModel >, Click on Add
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/199958792-e970ec5c-5aa7-4165-9edb-1607f2c60695.png)

```
Select the Model COntaines < EF Designer From Database >, Click on Next
```
![image](https://user-images.githubusercontent.com/111234771/199959051-ef6630ca-bb5f-497f-9a26-a1386fbd7af7.png)

```
Select Created Databases or Create a New Connection....
Save Connection Settings < StudentDBContext > (SimplilearnEFDBEntities). Click on Next
Select The Entity Version, Click on Next
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/199959262-11976e00-9d99-4152-93b4-b20407bd8181.png)

```
Select the tables (Departments, Student), 
Model Namespace < StudentModel > Click on Finish
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/199959402-a865fa43-4f79-4bf3-a1a0-516c502de714.png)

_Finally - Entity Data Modal_
![image](https://user-images.githubusercontent.com/111234771/199959814-175f688d-8960-47ec-ac2a-84e5ffa00def.png)

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
_Design Patter Tab_
![image](https://user-images.githubusercontent.com/111234771/199961651-9a32090d-f74d-486f-8197-f7bc59411e71.png)

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

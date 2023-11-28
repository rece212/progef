# progef



Create database Contacts ;
use Contacts;
create table tblContacts(
	[PersonID] int IDENTITY(1,1) NOT NULL PRIMARY KEY,
	[FirstName] varchar(255) not null,
	[LastName] varchar(255) not null,
	PhoneNumber varchar(10) not null,
	EmailAddress varchar(255) not null,
	Username varchar(255) not null,
	FOREIGN KEY (Username) REFERENCES tblUsers(Username)
);

create table tblUsers(
	Username varchar(255) not null PRIMARY KEY,
	[Password] varchar(255) not null
	);

insert into tblUsers values('Jack','1234'),('Reece','4321');

# Open Tools 
#cmd then Dev
then cd //Name of the folder( or do tab tab and will come up )

dotnet add package Microsoft.EntityFrameworkCore.SqlServer -v 5.0.17
dotnet add package Microsoft.EntityFrameworkCore.Design -v 5.0.17
dotnet tool install --global dotnet-ef

dotnet ef dbcontext scaffold "Server=tcp:classdb.database.windows.net,1433;Initial Catalog=Contacts;Persist Security Info=False;User ID=adminadmin;Password=@Password1;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;" Microsoft.EntityFrameworkCore.SqlServer -o Model

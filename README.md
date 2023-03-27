# Piek-uves-darbs
Datubāze ar darbiniekiem : vards, uzvards,epasts, parole

using System.Data.SqlClient;

// Definējam SQL pieprasījumu, lai izveidotu tabulu
string createTableQuery = @"
    CREATE TABLE Darbinieki (
        ID INT PRIMARY KEY IDENTITY,
        Vards NVARCHAR(50) NOT NULL,
        Uzvards NVARCHAR(50) NOT NULL,
        Epasts NVARCHAR(50) NOT NULL,
        Parole NVARCHAR(50) NOT NULL
    );
";

// Izveidojam savienojumu ar SQL Server datubāzi
string connectionString = "Data Source=myServerAddress;Initial Catalog=myDataBase;User ID=myUsername;Password=myPassword;";
SqlConnection connection = new SqlConnection(connectionString);
connection.Open();

// Izpildām SQL pieprasījumu, lai izveidotu tabulu
SqlCommand command = new SqlCommand(createTableQuery, connection);
command.ExecuteNonQuery();

// Aizveram savienojumu
connection.Close();

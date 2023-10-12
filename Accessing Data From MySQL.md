```cs

// ADD NUGET PACKAGE - MYSQL.DATA

using MySql.Data;
using MySql.Data.MySqlClient;

string connStr = "server=localhost;user=root;database=world;port=3306;password="PASSWORDHERE"; // STORE CONNECTION STRING
MySqlConnection connection = new MySqlConnection(connStr); // CREATE CONNECTION

try
{

    connection.Open(); //OPEN CONNECTION

    //DEFINE COMMAND
    string taskOneSqlCmd = "SELECT Name, Continent, LifeExpectancy FROM world.country \r\nWHERE LifeExpectancy > 78\r\norder by LifeExpectancy asc;";
    string taskTwoSqlCmd = "SELECT Name, Continent FROM world.country\r\nWHERE Continent = \"Europe\";";

    //CREATE COMMAND
    MySqlCommand cmd = new MySqlCommand(taskOneSqlCmd, connection);
    MySqlCommand cmd2 = new MySqlCommand(taskTwoSqlCmd, connection);

    //EXECUTE COMMAND
    MySqlDataReader reader = cmd.ExecuteReader();


    // DISPLAY RESULTS 
    while (reader.Read())
    {
        Console.WriteLine(reader[0] + " -- " + reader[1] + "--" + reader[2]);
    }
    reader.Close();

    reader = cmd2.ExecuteReader();

    while (reader.Read())
    {
        Console.WriteLine(reader[0] + " -- " + reader[1]);
    }
    reader.Close();

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
connection.Close(); // close the connection

```

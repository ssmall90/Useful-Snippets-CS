```cs

class Person
{
    public string _FirstName;
    public string _LastName;
    public int _Age;

    public Person() : this("Unknown", "Unknown", 0)
    {

    }

    public Person(int pAge) : this("Unknown", "Unknown", pAge)
    {

    }

    public Person(string pFirstName, string pLastName) : this (pFirstName,pLastName,0)
    {

    }
    public Person(string pFirstName, string pLastName, int pAge)
    {
        _FirstName = pFirstName;
        _LastName = pLastName;
        _Age = pAge;
            
        Console.WriteLine($"{_FirstName} {_LastName} {_Age}");
    }

}

```

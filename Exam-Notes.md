### Minesweeper Question
```cs
char[,] board = 
int result = 0;

for(int i = 0; i < board.GetLength(0); i++)
{
    for(int j = 0; j < board.GetLength(1); j++)
    {
        if (board[i,j] == 'X')
        {
            for(int di = -1; di <= 1; di++)
            {
                for(int dj = -1; dj <= 1; dj++)
                {
                    if(i + di >= 0 && i + di < board.GetLength(0)
                        && j + dj >= 0 && j + dj < board.GetLength(1) &&
                        board[i + di, j + dj] == ' ')
                    {
                        result++;
                    }
                }
            }
        }
    }
}
Console.WriteLine(result);
```
### FizzBuzz Question

```cs 
int ticks = 0;
int tocks = 0;
int tickTocks = 0;
int SHOCKS = 0;
int numbers = 0;

for(int i = 1; i <= 10000; i++)
{
    if(i % 3 == 0)
    {
        if(i % 5 == 0)
        {
            tickTocks++;
        }
        else
        {
            ticks++;
        }
    }
    else if(i % 5 == 0)
    {
        tocks++;
    }
    else if(i % 7 == 0)
    {
        SHOCKS++;
    }
    else
    {
        numbers++;
    }
}

Console.WriteLine($"{ticks}, {tocks}, {tickTocks}, {SHOCKS}, {numbers}");
```

### Hello Question

```cs
string[] testData =
{
    "hellohellohello",
    "hellolhlhello",
    "llhelloll",
    "hellehhollohhalla",
    
};

foreach(string data in testData)
{
    int count = 0;
    for(int i = 0; i < data.Length - 4; i++)
    {
        if (data[i] == 'h' &&
            data[i+1] == 'e' &&
            data[i+2] == 'l' &&
            data[i+3] == 'l' &&
            data[i+4] == 'o')
        {
            count++;
        }

        count = data.Split("hello").Length - 1;
    }

    Console.WriteLine(count);
}
```

### Consonants Question
```cs
string consonants = "bcdfghjklmnpqrstvwxyz";
string numbers = "0123456789";

string[] testData = { "ab", "22", "ab1cd23ef4gh", "55mememe5", "23AbBc4Dd",;
string data = "";
foreach (string test in testData)
{
    data = test.ToLower();
    int sumOfNumbers = 0;
    int numberOfConsonants = 0;

    for (int i = 0; i < data.Length; i++)
    {
        if (consonants.Contains(data[i]))
        {
            numberOfConsonants++;
        }
        else if (numbers.Contains(data[i]))
        {
            int number = int.Parse(data[i].ToString());
            number = 0;
            for (number = 0; number < numbers.Length; number++)
            {
                if (numbers[number] == data[i])
                {
                    break;
                }
            }
            number = data[i] - '0';

            sumOfNumbers += number;
        }
    }

    int result = sumOfNumbers * numberOfConsonants;
    Console.WriteLine(result);
}
```



```cs
int[] arr = new int[10] { 56, 1, 99, 67, 89, 23, 44, 12, 78, 34 };

int temp;
int smallest;

for (int i = 0; i < arr.Length - 1; i++)
{
    smallest = i;
    for (int j = i + 1; j < arr.Length; j++)
    {
        if (arr[j] < arr[smallest])
        {
            smallest = j;
        }
    }
    temp = arr[smallest];
    arr[smallest] = arr[i];
    arr[i] = temp;
}
```

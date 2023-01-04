```cs 
public int[] SortArray(int[] array, int length)
{
    for (int i = 1; i < length; i++)
    {
        var key = array[i];
        var flag = 0;
        for (int j = i - 1; j >= 0 && flag != 1;)
        {
            if (key < array[j])
            {
                array[j + 1] = array[j];
                j--;
                array[j + 1] = key;
            }
            else flag = 1;
        }
    }
    return array;
}
```

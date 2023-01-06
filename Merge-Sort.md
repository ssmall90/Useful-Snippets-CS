```cs 
// Merge Method
int[] Merge(int[] array1, int[] array2) 
{
    int[] mergedArray = new int[array1.Length + array2.Length];

    int i = 0;
    int j = 0;
    int k = 0;

    while (i < array1.Length && j < array2.Length)
    {
        if (array1[i] < array2[j])
        {
            mergedArray[k] = array1[i];
            i++;

        }
        else
        {
            mergedArray[k] = array2[j];
            j++;

        }
        k++;
    }
    while (i < array1.Length)
    {
        mergedArray[k] = array1[i];
        i++;
        k++;
    }
    while (j < array2.Length)
    {
        mergedArray[k] = array2[j];
        j++;
        k++;
    }

    return mergedArray;
}

//MergeSort Method
int[] MergeSort(int[] input, int start, int end)
{
    if (start >= end)
    {
        return new int[] { input[end] };
    }
    int middle = start + (end - start) / 2;

    int[] left = MergeSort(input, start, middle);
    int[] right = MergeSort(input, middle +1, end);

    int[] mergedArray = Merge(left, right);

    return mergedArray;
}

// Main Method

int[] ints = new int[] { 1, 22, 5, 42, 15, 6, 26 };

int[] mergedArray = MergeSort(ints, 0, ints.Length - 1);

foreach (int i in mergedArray)
{
    Console.WriteLine(i);
}

```

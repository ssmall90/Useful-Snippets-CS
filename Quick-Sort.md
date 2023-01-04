```cs
var numbers = new[] { 1, 5, 0, 34, 3, 9 };

sortArray(numbers);

foreach (var number in numbers)
{
    Console.WriteLine(number);
}

void sortArray(int[] numbers)
{
    quickSort(numbers, 0, numbers.Length - 1);
}

//QUICKSORT SECTION -----------------------------------

void quickSort(int[] numbers, int left, int right)
{
    int i = left;
    int j = right;

    var pivot = numbers[right];

    while (i <= j)
    {
        while (numbers[i] < pivot)

            i++;

        while (numbers[j] > pivot)

            j--;

        if (i <= j)
        {
            var temp = numbers[i];
            numbers[i] = numbers[j];
            numbers[j] = temp;

            i++;
            j--;
        }
    }

    if (left < j)
    {
        quickSort(numbers, left, j);
    }
    if (i < right)
    {
        quickSort(numbers, i, right);
    }
}

```

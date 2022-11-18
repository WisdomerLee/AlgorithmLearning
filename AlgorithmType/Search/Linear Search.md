참고링크 
https://www.geeksforgeeks.org/linear-search/

선형 탐색
가장 간단한 탐색 알고리즘

구현이 가장 단순함
배열 같은 곳의 자료 구조 등에서 맨 처음부터 맞는 오브젝트가 있는지 순차적으로 접근하여 맞는 오브젝트가 있는지 찾는 알고리즘

1번 찾는 경우
```C#
using System;

class LinearSearch
{
  public static int Search(int[] arr, int x)
  {
    int n = arr.Length;
    for(int i =0; i<n; i++)
    {
      if(arr[i]==x)
        return i;
    }
    return -1
  }
  
  public static void Main()
  {
    int[] arr = {2,3,4,10,40};
    int x = 10;
    int result = Search(arr, x);
    string comment = (result == -1) ? "Element is not present in array" : "Element is present at index"+result;
    Console.WriteLine(comment);
  }
}

```
여러 번 찾는 경우 : 재귀 용법 (재귀란? 내부에서 자기 자신의 함수를 호출할 때)
```C#
using System;

static class LinearSearch
{
  static int[] arr = {5, 15, 6, 9, 4};
  static int LinearSearch(int[] arr, int size, int key)
  {
    if(size==0)
    {
      return -1;
    }
    else if(arr[size-1]==key)
    {
      return size-1;
    }
    else
    {
      return LinearSearch(arr, size-1, key);
    }
  }
  public static void Main(string[] args)
  {
    int key = 4;
    
    int index = LinearSearch(arr, arr.Length, key);
    
    string comment = (index != -1) "The element " + key + "is found at " + index + "index of the given array." : "The element "+ key + "is not found.";
    Console.Write(comment);
  }
}

```

Non-repeating elements in an array in python
Here, in this page we will discuss the program to print the non-repeating elements in python programming language. We are given with an integer array and need to print those elements which occurs only one time.

Example
Input : arr[8] = [10, 20, 70, 90, 80, 20, 10, 20]
Output : 70 90 80
Explanation : 70, 90 and 80 are occur 1 time in the given array, 10 occurs 2 times and 20 occurs 3 times.
Methods Discussed :
Method 1 : Using Two for loops
Method 2 : Using dictionary
Method 1 :
In this method we will count the frequency of each elements using two for loops and print those elements which have frequency equals to one.

To check the status of visited elements create a array of size n.
Run a loop from index 0 to n and check if (visited[i]==1) then skip that element.
Otherwise create a variable count = 1 to keep the count of frequency.
Run a loop from index i+1 to n
Check if(arr[i]==arr[j]), then increment the count by 1 and set visited[j]=1.
After complete iteration of inner for loop and check if count == 1 then print those element.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(n)
Method 1 : Code in Python
Run
# Python 3 program to count unique elements
def count(arr, n):

   # Mark all array elements as not visited
   visited = [False for i in range(n)]

   # Traverse through array elements
   # and count frequencies
   for i in range(n):

     # Skip this element if already
     # processed
     if (visited[i] == True):
        continue

     # Count frequency
     count = 1
     for j in range(i + 1, n, 1):
        if (arr[i] == arr[j]):
          visited[j] = True
          count += 1
     if count == 1 :
        print(arr[i]);
   

# Driver Code
arr = [10, 30, 40, 20, 10, 20, 50, 10]
n = len(arr)
count(arr, n)
Output
30
40
50
Related Pages
Counting Distinct Elements in an Array

Finding  Repeating elements in an Array

Removing Duplicate elements from an array

Finding Minimum scalar product of two vectors

Finding Maximum scalar product of two vectors in an array 

Method 2 :
In this method we will count use dictionary to count the frequency of each elements and then check if that frequency is equal to 1 or not.

Declare a dictionary dict() say, mp = dict().
Start iterating over the entire array
If element is present in map, then increase the value of frequency by 1.
Otherwise, insert that element in map.
After complete iteration over array, start traversing map and check if value is equal to 1,then print the key value.
Time and Space Complexity:
Time Complexity : O(n)
Space Complexity : O(n)
Non-repeated in python
Method 2 : Code in Python
Run
def count(arr, n):

    mp = dict()
  
    # Traverse through array elements
    # and count frequencies

    for i in range(n):
        if arr[i] in mp.keys():
            mp[arr[i]] += 1
        else:
            mp[arr[i]] = 1

           
    # Traverse through map and print
    # frequencies

    for x in mp:
        if mp[x]==1 :
          print(x);
   
# Driver Code 
arr = [10, 30, 40, 20, 10, 20, 50, 10] 
n = len(arr) 
count(arr, n)
Output
30 40 50

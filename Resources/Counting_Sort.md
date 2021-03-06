# COUNTING SORT
It is a linear-time sorting algorithm based on keys between a specific range. It counts the number of objects having distinct key values. An arithmetic is performed to calculate the positions of numbers.<br> 
The steps and execution of counting sort is explained briefly with the help of an example.<br>
## ANALYSIS
Let us consider the data in the range of 0 to 7.<br>
Input Data: 1,4,1,2,7,5,2<br>
Index of array element is written above the diagrammatic representation.<br>
We take a count array to store the count of each unique object.<br>
Index  ->  0     1      2      3      4     5      6      7<br>
Element->  0     2      2      0      1     1      0      1<br>
This is the initial position of elements.<br>
#### 1st pass: 
Modify the count array such that each element at each index stores the sum of previous counts. The modified count array indicates the position of each object in the output sequence.<br> 
Index  ->  0     1      2      3      4     5      6      7<br>
Element->  0     2      4      4      5     6      6      7<br>
#### 2nd pass:
Output each object from the input sequence followed by decreasing its count by 1. Process the input data: 1, 4, 1, 2, 7, 5, 2. Position of 1 is 1. Put data 1 at index 1 in output. Decrease count by 1 to place next data 1 at an index 0 smaller than this index.  Shown below is the output array -<br>
Index  ->  0     1      2      3      4     5      6<br>
Element->  1     1      2      2      4     5      7<br>
## Pseudocode:
1)	n-> no of input elements, A[n] -> array of elements.<br>
2)	Initially, k=0. While entering the elements in array,<br>
        if (A[i] > k) then k=A[i];<br>
3)	Now pass, A[n], n, & k to the counting sort function.<br>
4)	In counting sort function, take two temporary arrays, B[n] & C[k].<br>
for (i = 0; i <= k; i++)   ->  C[i] = 0;<br>
for (j = 0; j < n; j++)     ->  C[A[j]] = C[A[j]] + 1;<br>
for (i = 1; i <= k; i++)    ->  C[i] = C[i] + C[i-1];<br>
for (j = n-1; j >= 0; j--)<br>
	C[A[j]] = C[A[j]] - 1;<br>
       	B[C[A[j]]] = A[j];<br>
The sorted array is given by B[n].<br>
## Time & Space Complexity of the Algorithm
Worst Case Time & Space Complexity [ Big-O]: O(n + k) where k is the range of the non-negative key values.



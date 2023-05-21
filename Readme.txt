gitREQUIREMENTS:

1. Each time work only with the first i-1 element from of the array

2. Pick element arr[i] and insert it into sorted sequence in the array from 0 to i-1.

3. Use of two counters.


CODE IN JAVASCRIPT:

function sort(arr) {
  const length = arr.length;
  
  for (let i = 1; i < length; i++) {
    let j = i - 1;
    const current = arr[i];
    
    while (j >= 0 && arr[j] > current) {
      arr[j + 1] = arr[j];
      j--;
    }
    
    arr[j + 1] = current;
  }
  
  return arr;
}

// Example
const array = [5, 3, 8, 2, 1, 4];
console.log("Before sorting:", array);
console.log("After sorting:", sort(array));

EXPLANATION:

In this code, we introduce an additional counter "k" to keep track of the current position that needs to be updated during the shifting of larger elements. 
The first counter "i" is used to iterate through the array and pick the element arr[i] to be inserted into the sorted sequence from index 0 to i-1.
During the iteration, it compares the current element with the preceding elements (arr[j] > current) and shifts the larger elements one position to 
the right by updating the value at index 'k' and moving 'k' to the left (k = j). The counter j is decremented until it reaches the beginning of the
sorted sequence.

Finally, it places the current element in its correct position by assigning current to arr[k].

The resulting sorted array is returned by the "sort" function. In the example usage, 
we have an array '[5, 3, 8, 2, 1, 4]', and the sorted array '[1, 2, 3, 4, 5, 8]' is printed to the console.








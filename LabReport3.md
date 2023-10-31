# Lab Report 3
Junrong Chen

## Part 1: Bugs
### Code to test:
```Java
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
### Failure-inducing jUnit test:
```Java
@Test
public void testReverseInPlace_FailureInducing() {
  int[] input = {1, 2, 3, 4, 5};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input);
}
```
### Not-Failure-inducing jUnit test:
```Java
@Test
public void testReverseInPlace_NonFailureInducing() {
  int[] input = {10, 20, 30, 40, 50};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[]{50, 40, 30, 20, 10}, input);
}
```
### Symptom - Output of Running Tests
![sympton](https://github.com/JunrongChen2004/CSE15L/assets/122309066/cb66043b-b1dc-4581-a072-f1840870de2e)

### Bug Fix
#### Before:
```Java
arr[i] = arr[arr.length - i - 1];
```
#### After (Fixed code for both methods):
```Java
int temp = arr[i];
arr[i] = arr[arr.length - i - 1];
arr[arr.length - i - 1] = temp;
```
The fix swaps elements properly by using a temporary variable to hold the value before assigning it to the reversed index. This addresses the issue by correctly storing the original element to be reassigned at its respective reversed index.

## Part 2: Researching Commands
### Command 'grep'
#### -i
##### files
```Bash
grep -i "pattern" file.txt
```

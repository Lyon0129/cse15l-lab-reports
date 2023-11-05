testReversed1 will cause failure, testRerversed2 will success.
```
@Test
public void testReversed1(){
  int[] input2 = {1,2,3,4,5};
  assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input2));
}

@Test
public void testRerversed2(){
  int[] input3 = {0,0,0};
  assertArrayEquals(new int[]{0,0,0},ArrayExamples.reversed(input3) );
}
}


```
```

public class ArrayExamples {
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
}
```
<img width="751" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/7891cb29-6a6c-4066-b94f-4aed356fee2d">
before
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
after                       
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i++) {
        newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```


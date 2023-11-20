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
```                       
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
We updating the values of the wrong array, so I changed it, so that we update a newarray instead, also I changed the return value.

# part2
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/0041af3f-55b7-460a-9b80-0668e7976085)
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/d0f70473-fd17-4c42-a91d-6e90e15250dd)
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/ff6fec61-21a3-495f-843b-e0ed6d2ea928)

<img width="1068" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/31c02511-0896-4e6a-add2-ea465c58363c">
The ls -R command lists the contents of a directory recursively, meaning that it doesn't just list the target you provide for it, but also descends into every subdirectory within that target (and every subdirectory in each subdirectory, and so on.) 

1.This is use type f, d to find files.
```find./technical -type f >"456.txt" ```
```find./technical -type d >"234.txt" ```
<img width="863" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/472c097d-fdec-41c5-a044-9f8d5124fab4">
<img width="1008" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/81045bde-5113-492e-b211-da6bcf5d53b8">
<img width="872" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/f4b98ff1-7df5-42a5-ba4f-8fd60f478090">
<img width="543" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/dd32c00d-ac64-4028-8ded-d58763fe959f">

2. This is using typef, d to find Files by Extension
``` find./technical -type d -name "*.png" >"789.txt" ```
``` find./technical -type f -name "*.png" >"789.txt" ```
<img width="993" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/4d285224-88ba-4f7d-aacc-dd943063b8b5">
<img width="618" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/5e633592-c77b-449b-8b78-c4ef7df09789">
<img width="1029" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/555e478f-c504-4c5a-bc5a-4ad7f48a8706">
<img width="865" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/09b19b2b-e4e2-4db5-991d-9ed81c7f02d4">

3.This is using typef, d to find Files by size.
``` find./technical -type f -size +1k -size -2k >"000.txt" ```
``` find./technical -type d -size +3k -size -5k >"010.txt" ```
<img width="1073" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/b6eb48af-00ce-44a5-89bd-b1be54616499">
<img width="713" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/4d278591-745a-4c9e-9c05-3518831403ab">
<img width="1037" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/c8e6c092-d203-4f02-b2b5-1af9e5c8db7f">
<img width="432" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/32906f41-694e-4404-8355-be999906f96c">

4.This is using typef, d find Files Modified in the Last Day.
``` find./technical -type d -mtime -1 >"111.txt" ```
``` find./technical -type f -mtime -1 >"121.txt" ```
<img width="959" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/68ef65c3-3e47-4ee8-8082-2970a23da3ea">
<img width="512" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/1d4c35c6-a2c4-4e1c-b11e-e7d5b0a2cafc">
<img width="1088" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/ae2ff48b-9193-4b9e-9a83-6775aba205c9">

[https://linux.die.net/man/1/find] all of sources are come from this website.

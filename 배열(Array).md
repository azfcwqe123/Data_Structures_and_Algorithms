# 배열

### 배열의 첫번째 위치에 추가, O(1+n) = O(n)

```java
import java.util.Arrays;

public class ArrayMain {
    public static void main(String[] args) {

        int[] arr = {2,3,4,5,6};

        addFirst(arr, 1); 
        
        System.out.println(Arrays.toString(arr));

    }

    static void addFirst(int[] arr, int newValue) {

        for(int i = arr.length -1; i > 0; i--) {
            arr[i] = arr[i-1];
        }
        
        arr[0] = newValue;
    }
}


```

```
[1, 2, 3, 4, 5]
```

1. 배열의 맨 끝에 있는 인덱스 위치부터 시작한다 -> arr[arr.length-1]

2. 배열의 두번째 인덱스(arr[1])에 오면 순회를 끝낸다. -> arr[1],

3. 배열의 첫번째 위치에 넣고자 하는 값을 추가한다. -> arr[0] = 1;

---

### 배열의 특정 위치에 추가, O(1 + n/2) = O(n)

```java
import java.util.Arrays;

public class ArrayMain {
    public static void main(String[] args) {

        int[] arr = {2,3,4,5,6};

        addSpecific(arr, 2, 100);

        System.out.println(Arrays.toString(arr));

    }

    static void addSpecific(int[] arr, int index, int newValue) {
        for (int i = arr.length-1; i>index; i--) {
            arr[i] = arr[i-1];
        }
        arr[index] = newValue;
    }

}

```

```
[2, 3, 100, 4, 5]
```

1. 인덱스를 넣을 위치, 어떤 값을 넣을지 정한다. -> addSpecific(arr, 2, 3)
2. 배열의 맨 끝에 있는 인덱스 위치부터 시작한다 -> arr[arr.length-1]
3. 배열의 특정 인덱스 뒤까지 순회한다. -> index+1까지만 순회한다.
4. 배열의 특정 인덱스에 값을 추가한다. -> arr[index] = newValue;

---

### 배열의 마지막 위치에 추가, O(1)

```java
import java.util.Arrays;

public class ArrayMain {
    public static void main(String[] args) {

        int[] arr = {2,3,4,5,6};

        addLast(arr, 100);

        System.out.println(Arrays.toString(arr));

    }
    
    static void addLast(int[] arr, int newValue) {
        arr[arr.length-1] = newValue;
    }

}

```

```
[2, 3, 4, 5, 100]
```

1. arr[arr.length-1]에 새로운 값을 대입한다.

---

### 버블 정렬

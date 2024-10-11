## 버블 정렬

```java
import java.util.Arrays;

public class ArrayMain {
    public static void main(String[] args) {

        int[] arr = {5, 4, 3, 2, 1};

        int n = arr.length;

        // 시간 복잡도: O(n^2)
        for(int i=0; i<n-1; i++) { // 정렬해야하는 요소 개수 n-1개. 요소 1개는 자연스럽게 자동으로 된다고 보면 된다.
            for(int j=0; j<n-i-1; j++) { // 마지막 i개 요소는 정렬 돼있으니 n-i-1번 순회
                if(arr[j] > arr[j+1]) { // 앞의 요소가 뒤의 요소보다 크면 바꾼다.
                    int tmp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = tmp;
                }
            }
        }

        System.out.println(Arrays.toString(arr));
    }
}

```

```
1 2 3 4 5
```

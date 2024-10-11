## 삽입 정렬

```java
import java.util.Arrays;

public class ArrayMain {
    public static void main(String[] args) {

        int[] arr = {5, 3, 2, 4, 1};

        int n = arr.length;

        // 시간 복잡도 O(n^2)
        for(int i=1; i<n; i++) {

            int key = arr[i]; // arr[i]부터 시작.
            int j = i-1; // arr[i-1]부터 비교해줌, 핵심

            while(j>=0 && arr[j] > key) { // 인덱스가 arr[0] 이상이고, arr[i-1]이 arr[i]보다 크면 성립
                arr[j+1] = arr[j]; // 조건이 성립한다면 옆칸으로 밀기
                j--; // 다음엔 arr[i-2]가 arr[i-1]보다 큰 지 비교
            }
            arr[j+1] = key; // arr[j] 뒤인 arr[j+1]에 마지막 처리
        }

        System.out.println(Arrays.toString(arr));
    }
}

```

```
[1, 2, 3, 4, 5]
```

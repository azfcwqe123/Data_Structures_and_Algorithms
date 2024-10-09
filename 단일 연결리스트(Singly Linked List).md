```java
package LinkedList;

public class LinkedList<E> {

    private Node<E> head;
    private int size = 0;
    
    public void add(E e, int index) { // 특정 위치에 삽입
        Node<E> newNode = new Node<>(e);

        if(index == 0) {
            newNode.next = head;
            head = newNode;
        } else {
            Node<E> currentNode = head;

            for(int i=0; i<index-1; i++) {
                currentNode = currentNode.next;
            }
            newNode.next = currentNode.next;
            currentNode.next = newNode;
        }
        size++;
    }

    public void addFirst(E e) { // 첫번쨰 인덱스에 노드 추가
        Node<E> newNode = new Node<>(e);
        newNode.next = head;
        head = newNode;
        size++;
    }

    public void addLast(E e) { // 마지막 인덱스에 노드 추가
        Node<E> newNode = new Node<>(e);

        if(head == null) {
            head = newNode;
        } else {
            Node<E> currentNode = head;
            while(currentNode.next != null) {
                currentNode = currentNode.next;
            }
            currentNode.next = newNode;
        }
        size++;
    }

    public void remove(int index) {

        if(index == 0) { // 첫번째 노드 제거
            head = head.next;
        } else { // 특정 인덱스의 노드 제거
            Node<E> currentNode = head;

            for(int i=0; i<index-1; i++) {
                currentNode = currentNode.next;
            }
            currentNode.next = currentNode.next.next;
        }
        size--;
    }

    public void removeFirst() { // 첫번째 노드 제거
        head = head.next;
        size--;
    }

    public void removeLast() { // 마지막 노드 제거
        Node<E> currentNode = head;

        while(currentNode.next.next != null) {
            currentNode = currentNode.next;
        }
        currentNode.next = null;
        size--;
    }

    public E get(int index) { // 특정 인덱스 요소 반환
        Node<E> currentNode = head;
        for(int i=0; i<index; i++) {
            currentNode = currentNode.next;
        }
        return currentNode.data;
    }

    public E getFirst() { // 첫번째 인덱스 요소를 반환
        return head.data;
    }

    public E getLast() { // 마지막 인덱스 요소를 반환
        Node<E> currentNode = head;
        for(int i=0; i<size-1; i++) {
            currentNode = currentNode.next;
        }
        return currentNode.data;
    }

    public void clear() { // 모든 요소 제거
        head = null;
    }

    public void show() { // 리스트 출력
        Node<E> x = head;
        StringBuilder sb = new StringBuilder();

        while(x != null) {
            sb.append(x.data);
            if(x.next != null) {
                sb.append("->");
            }
            x = x.next;
        }

        System.out.println(sb.toString());
    }

    public boolean isEmpty() { // 리스트가 비었는지
        return size == 0;
    }

    public int size() { // 리스트 크기 반환
        return size;
    }

}

```

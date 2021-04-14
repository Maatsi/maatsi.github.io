---
title: "[Leetcode] 206. Reverse Linked List (Python)"
tags:
  - Data Structures and Algorithms
  - Leetcode
  - Linked List
categories:
  - Data Structures and Algorithms
---


## Explanation
링크드 리스트 뒤집기는 기본적이고, 정말 많이 나오는 알고리즘중 하나입니다. 시간복잡도는 O(n)이며, 총 3개의 스텝으로 이루어집니다. 이미지와 함께하면 이해가 빠를겁니다. [출처](https://www.youtube.com/watch?v=D7y_hoT_YZI)

1. 3개의 포인터를 (prev,curr,next_node) 선언하고 다음 노드의 주소 복사한다. next_node를 curr.next에 선언함으로써 복사가 되는것이고, prev노드는 빈 더미노드이다.  
![노드어싸인](https://user-images.githubusercontent.com/33334078/114651636-532df580-9d1f-11eb-9c34-9a5f77a94fe2.gif)

2. 현재노드와 다음노드의 링크를 끊고, 그 포인터를 전 노드로 연결한다.

3. 포인터 이동하기
![다음노드](https://user-images.githubusercontent.com/33334078/114651889-c8012f80-9d1f-11eb-9b0d-37ced4166382.gif)


반복하다보면 이런 형태가 됩니다. curr == null인 상태가 왔으므로, while문이 끝나게 되고, 마지막노드인 prev를 리턴합니다.  
![IMG_8365](https://user-images.githubusercontent.com/33334078/114653800-cdf90f80-9d23-11eb-81ec-fac1103896ad.jpg)



## Example
#### Example 1
```
Input: 1->2->3->4->5
Output: 5->4->3->2->1
```



## Code Implementation

```python
def reverseList(self, head: ListNode) -> ListNode:
    prev = None
    curr = head
    next_node = ListNode

    while curr != None:
      next_node = curr.next     # 다음노드 복사 (한칸이동)
      curr.next = prev      # 포인터 끊고 전노드에 연결
      prev = curr     # 한칸 이동
      curr = next_node     # 한칸 이동
    return prev
```

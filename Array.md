### Bài toán

Cho một mảng số nguyên **`nums`**. Hãy tạo một mảng số nguyên mới **`differenceArray`** có **cùng độ dài** với `nums`.

Mỗi phần tử của `differenceArray`, tức là **`differenceArray[i]`**, được tính như sau:

1. Tính **tổng tất cả các phần tử bên trái** của vị trí `i` trong mảng `nums`, gọi là **`leftSum_i`**.
2. Tính **tổng tất cả các phần tử bên phải** của vị trí `i` trong mảng `nums`, gọi là **`rightSum_i`**.
3. Lấy **giá trị tuyệt đối** của hiệu hai tổng đó:

[
differenceArray[i] = | leftSum_i - rightSum_i |
]

Nếu **không có phần tử** ở bên trái hoặc bên phải của `i`, thì tổng tương ứng được xem là **0**.

---

## Ví dụ

### Ví dụ 1

**Input**

```
nums = [2, 5, 1, 6, 1]
```

**Output**

```
[13, 6, 0, 7, 14]
```

**Giải thích**

* `i = 0`

  * leftSum = 0
  * rightSum = 5 + 1 + 6 + 1 = 13
  * |0 − 13| = **13**

* `i = 1`

  * leftSum = 2
  * rightSum = 1 + 6 + 1 = 8
  * |2 − 8| = **6**

* `i = 2`

  * leftSum = 2 + 5 = 7
  * rightSum = 6 + 1 = 7
  * |7 − 7| = **0**

* `i = 3`

  * leftSum = 2 + 5 + 1 = 8
  * rightSum = 1
  * |8 − 1| = **7**

* `i = 4`

  * leftSum = 2 + 5 + 1 + 6 = 14
  * rightSum = 0
  * |14 − 0| = **14**

---

### Ví dụ 2

**Input**

```
nums = [3, 3, 3]
```

**Output**

```
[6, 0, 6]
```

**Giải thích**

* `i = 0`
  |0 − (3 + 3)| = **6**

* `i = 1`
  |3 − 3| = **0**

* `i = 2`
  |(3 + 3) − 0| = **6**

---

### Ví dụ 3

**Input**

```
nums = [1, 2, 3, 4, 5]
```

**Output**

```
[14, 11, 6, 1, 10]
```

---

## Ràng buộc

* `1 ≤ nums.length ≤ 1000`
* `1 ≤ nums[i] ≤ 100000`


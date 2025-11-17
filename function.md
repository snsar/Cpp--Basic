
# ## Phần 1 — Hàm Sử Dụng **Tham Trị**

---

## **Bài 1 — In dãy số chẵn/lẻ**

**Đề bài:**
Nhập số nguyên `n ≥ 1`. In ra các số từ `1 → n`, mỗi số kèm `(EVEN)` hoặc `(ODD)`.

**Input**

```
n
```

**Output**

```
1(ODD) 2(EVEN) ...
```

**Ví dụ**

```
Input:   5
Output:  1(ODD) 2(EVEN) 3(ODD) 4(EVEN) 5(ODD)
```

**Hàm tham trị**

```cpp
void printEvenOdd(int n);
```

---

## **Bài 2 — Tính tổng các số lẻ đến n**

**Đề bài:**
Tính tổng các số lẻ từ 1 đến n.

**Input**

```
n
```

**Output**
Tổng số lẻ.

**Ví dụ**

```
Input:  7
Output: 16
```

**Hàm tham trị**

```cpp
int sumOdd(int n);
```

---

## **Bài 3 — Kiểm tra số nguyên tố**

**Đề bài:**
Cho số nguyên dương n, kiểm tra có phải số nguyên tố hay không.

**Input**

```
n
```

**Output**

```
YES hoặc NO
```

**Ví dụ**

```
Input:  11
Output: YES
```

**Hàm tham trị**

```cpp
bool isPrime(int n);
```

---

## **Bài 4 — Tính giai thừa**

**Đề bài:**
Tính giai thừa `n!`.

**Input**

```
n
```

**Output**
Giá trị giai thừa.

**Ví dụ**

```
Input:  5
Output: 120
```

**Hàm tham trị**

```cpp
long long factorial(int n);
```

---

## **Bài 5 — Đếm số chữ số**

**Đề bài:**
Đếm số chữ số của một số nguyên dương.

**Input**

```
n
```

**Output**
Số chữ số.

**Ví dụ**

```
Input:  12345
Output: 5
```

**Hàm tham trị**

```cpp
int countDigits(int n);
```

---

# ## Phần 2 — Hàm Sử Dụng **Tham Chiếu**

---

## **Bài 6 — Hoán đổi 2 số**

**Đề bài:**
Dùng hàm hoán đổi giá trị hai số nguyên.

**Input**

```
a b
```

**Output**

```
a = ..., b = ...
```

**Ví dụ**

```
Input:   2 5
Output:  a = 5, b = 2
```

**Hàm tham chiếu**

```cpp
void swap(int &a, int &b);
```

---

## **Bài 7 — Tăng mỗi phần tử mảng lên 1**

**Đề bài:**
Cho mảng n phần tử, tăng mỗi phần tử lên 1.

**Input**

```
n
a1 a2 ... an
```

**Output**
Mảng sau khi tăng.

**Ví dụ**

```
Input:
3
4 6 7
Output:
5 7 8
```

**Hàm tham chiếu**

```cpp
void incrementArray(int a[], int n);
```

---

## **Bài 8 — Gán giá trị tuyệt đối**

**Đề bài:**
Chuyển biến x thành |x| bằng hàm tham chiếu.

**Input**

```
x
```

**Output**

```
|x|
```

**Ví dụ**

```
Input:  -15
Output: 15
```

**Hàm tham chiếu**

```cpp
void makeAbs(int &x);
```

---

## **Bài 9 — Tính tổng qua biến tham chiếu**

**Đề bài:**
Tính `res = a + b` và trả kết quả qua biến tham chiếu.

**Input**

```
a b
```

**Output**

```
res
```

**Ví dụ**

```
Input:  6 9
Output: 15
```

**Hàm tham chiếu**

```cpp
void add(int a, int b, int &res);
```

---

## **Bài 10 — Chuyển chuỗi sang chữ hoa**

**Đề bài:**
Dùng tham chiếu để biến đổi chuỗi: ký tự thường → in hoa.

**Input**

```
str
```

**Output**

```
STR
```

**Ví dụ**

```
Input:  abcDef
Output: ABCDEF
```

**Hàm tham chiếu**

```cpp
void toUpper(string &s);
```
---


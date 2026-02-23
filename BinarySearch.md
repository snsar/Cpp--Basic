## **Bài 1: Kiểm tra sự tồn tại (Cơ bản)**

**Mô tả**
Cho mảng số nguyên đã được **sắp xếp tăng dần** gồm `N` phần tử và số nguyên `X`. Hãy dùng tìm kiếm nhị phân để kiểm tra `X` có trong mảng không.

**Input**
* Dòng 1: `N` và `X`
* Dòng 2: `N` số nguyên (tăng dần)

**Output**
* `YES` nếu tìm thấy, ngược lại `NO`.

**Ví dụ**
```
Input:
5 7
1 3 5 7 9

Output:
YES
```

---

## **Bài 2: Vị trí đầu tiên của X**

**Mô tả**
Cho mảng đã sắp xếp tăng dần gồm `N` phần tử. Tìm vị trí (index) đầu tiên của phần tử có giá trị bằng `X`. Nếu không thấy, in `-1`.

**Input**
* Dòng 1: `N` và `X`
* Dòng 2: `N` số nguyên

**Output**
* Chỉ số đầu tiên của `X`.

**Ví dụ**
```
Input:
6 3
1 2 3 3 3 4

Output:
2
```

---

## **Bài 3: Vị trí cuối cùng của X**

**Mô tả**
Cho mảng đã sắp xếp tăng dần gồm `N` phần tử. Tìm vị trí (index) cuối cùng của phần tử có giá trị bằng `X`. Nếu không thấy, in `-1`.

**Input**
* Dòng 1: `N` và `X`
* Dòng 2: `N` số nguyên

**Output**
* Chỉ số cuối cùng của `X`.

**Ví dụ**
```
Input:
6 3
1 2 3 3 3 4

Output:
4
```

---

## **Bài 4: Số lượng phần tử bằng X**

**Mô tả**
Cho mảng đã sắp xếp tăng dần gồm `N` phần tử. Đếm số lượng phần tử có giá trị bằng `X`. (Gợi ý: Dùng tìm kiếm nhị phân tìm vị trí đầu và cuối).

**Input**
* Dòng 1: `N` và `X`
* Dòng 2: `N` số nguyên

**Output**
* Số lượng phần tử bằng `X`.

**Ví dụ**
```
Input:
6 3
1 2 3 3 3 4

Output:
3
```

---

## **Bài 5: Tìm số nhỏ nhất không nhỏ hơn X (Lower Bound)**

**Mô tả**
Cho mảng đã sắp xếp tăng dần gồm `N` phần tử. Tìm giá trị nhỏ nhất trong mảng mà lớn hơn hoặc bằng `X`. Nếu tất cả các phần tử đều nhỏ hơn `X`, in `-1`.

**Input**
* Dòng 1: `N` và `X`
* Dòng 2: `N` số nguyên

**Output**
* Giá trị tìm được hoặc `-1`.

**Ví dụ**
```
Input:
5 4
1 2 3 5 6

Output:
5
```

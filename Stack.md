# Stack (Ngăn xếp)

## Bài 1: Kiểm tra chuỗi ngoặc hợp lệ

**Mô tả**
Cho một chuỗi chỉ chứa các ký tự `(`, `)`, `[`, `]`, `{`, `}`. Kiểm tra xem chuỗi đó có phải là chuỗi ngoặc hợp lệ không (mỗi ngoặc mở phải được đóng đúng thứ tự).

**Input**
Một dòng chứa chuỗi ký tự (độ dài ≤ 10^4).

**Output**
In ra `YES` nếu hợp lệ, `NO` nếu không.

**Ví dụ**
Input: `{[()]}`
Output: `YES`

Input: `{[(]}`
Output: `NO`

**Gợi ý**
Dùng stack: khi gặp ngoặc mở thì push vào, khi gặp ngoặc đóng thì kiểm tra top của stack có phải ngoặc mở tương ứng không.

**Lời giải**
```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

int main() {
    string s;
    cin >> s;

    stack<char> st;
    for (char ch : s) {
        if (ch == '(' || ch == '[' || ch == '{') {
            st.push(ch);
        } else {
            if (st.empty()) {
                cout << "NO\n";
                return 0;
            }
            char top = st.top();
            st.pop();
            if ((ch == ')' && top != '(') ||
                (ch == ']' && top != '[') ||
                (ch == '}' && top != '{')) {
                cout << "NO\n";
                return 0;
            }
        }
    }

    cout << (st.empty() ? "YES" : "NO") << "\n";
    return 0;
}
```
**Giải thích:** Duyệt từng ký tự trong chuỗi. Nếu là ngoặc mở thì đẩy vào stack. Nếu là ngoặc đóng thì lấy phần tử trên cùng của stack ra và so sánh — nếu không khớp hoặc stack rỗng thì chuỗi không hợp lệ. Cuối cùng, stack phải rỗng thì chuỗi mới hợp lệ hoàn toàn.

---

## Bài 2: Đảo ngược chuỗi bằng Stack

**Mô tả**
Nhập một chuỗi, dùng stack để đảo ngược chuỗi đó và in ra kết quả.

**Input**
Một dòng chứa chuỗi (không có khoảng trắng, độ dài ≤ 1000).

**Output**
Chuỗi sau khi đảo ngược.

**Ví dụ**
Input: `hello`
Output: `olleh`

**Lời giải**
```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

int main() {
    string s;
    cin >> s;

    stack<char> st;
    for (char ch : s) {
        st.push(ch);
    }

    string result = "";
    while (!st.empty()) {
        result += st.top();
        st.pop();
    }

    cout << result << "\n";
    return 0;
}
```
**Giải thích:** Push từng ký tự vào stack (LIFO — vào sau ra trước). Sau đó pop lần lượt ra, ký tự cuối cùng sẽ xuất hiện đầu tiên, tạo thành chuỗi đảo ngược.

---

## Bài 3: Tính giá trị biểu thức hậu tố (Postfix)

**Mô tả**
Cho một biểu thức hậu tố (Reverse Polish Notation) gồm các số nguyên và các phép toán `+`, `-`, `*`, `/`. Tính giá trị của biểu thức đó.

**Input**
Một dòng chứa các token cách nhau bởi dấu cách.

**Output**
Kết quả là một số nguyên.

**Ví dụ**
Input: `3 4 + 2 *`
Output: `14`

Input: `5 1 2 + 4 * + 3 -`
Output: `14`

**Gợi ý**
Duyệt từng token: nếu là số thì push vào stack, nếu là toán tử thì pop 2 số ra, tính kết quả rồi push lại.

**Lời giải**
```cpp
#include <iostream>
#include <stack>
#include <sstream>
#include <string>
using namespace std;

int main() {
    string line;
    getline(cin, line);
    istringstream iss(line);

    stack<int> st;
    string token;
    while (iss >> token) {
        if (token == "+" || token == "-" || token == "*" || token == "/") {
            int b = st.top(); st.pop();
            int a = st.top(); st.pop();
            if (token == "+") st.push(a + b);
            else if (token == "-") st.push(a - b);
            else if (token == "*") st.push(a * b);
            else st.push(a / b);
        } else {
            st.push(stoi(token));
        }
    }

    cout << st.top() << "\n";
    return 0;
}
```
**Giải thích:** Biểu thức hậu tố được tính bằng cách dùng stack. Với mỗi số, push vào stack. Với mỗi toán tử, pop 2 phần tử (b trước, a sau — vì stack LIFO), tính `a op b` rồi push kết quả lại. Phần tử cuối cùng trong stack là kết quả.

---

## Bài 4: Tìm phần tử nhỏ nhất trong Stack trong O(1)

**Mô tả**
Thiết kế một stack hỗ trợ 3 thao tác:
- `push x`: thêm x vào stack
- `pop`: xóa phần tử trên cùng
- `getMin`: trả về phần tử nhỏ nhất hiện có trong stack

Tất cả thao tác phải chạy trong O(1).

**Input**
Dòng đầu: số lượng thao tác Q (Q ≤ 10^5).
Mỗi dòng tiếp theo: một trong các lệnh `push x`, `pop`, `getMin`.

**Output**
Với mỗi lệnh `getMin`, in ra giá trị nhỏ nhất.

**Ví dụ**
Input:
```
6
push 5
push 3
push 7
getMin
pop
getMin
```
Output:
```
3
3
```

**Gợi ý**
Dùng 2 stack: một stack chính và một stack phụ lưu giá trị min tại mỗi thời điểm.

**Lời giải**
```cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

int main() {
    int q;
    cin >> q;

    stack<int> mainStack;
    stack<int> minStack; // top luôn là giá trị min hiện tại

    while (q--) {
        string op;
        cin >> op;

        if (op == "push") {
            int x;
            cin >> x;
            mainStack.push(x);
            if (minStack.empty() || x <= minStack.top()) {
                minStack.push(x);
            }
        } else if (op == "pop") {
            if (mainStack.top() == minStack.top()) {
                minStack.pop();
            }
            mainStack.pop();
        } else { // getMin
            cout << minStack.top() << "\n";
        }
    }

    return 0;
}
```
**Giải thích:** Dùng `minStack` để theo dõi giá trị min. Khi push một giá trị `x`, nếu `x` nhỏ hơn hoặc bằng min hiện tại thì cũng push vào `minStack`. Khi pop, nếu phần tử bị xóa bằng với top của `minStack` thì cũng pop `minStack`. `getMin` chỉ cần đọc top của `minStack` — O(1).

---

## Bài 5: Dãy số tiếp theo lớn hơn (Next Greater Element)

**Mô tả**
Cho mảng gồm N số nguyên. Với mỗi phần tử, tìm phần tử lớn hơn đầu tiên xuất hiện ở bên phải nó trong mảng. Nếu không có, in ra `-1`.

**Input**
Dòng đầu: N (1 ≤ N ≤ 10^5).
Dòng hai: N số nguyên cách nhau bởi dấu cách.

**Output**
N số nguyên — kết quả cho từng phần tử, cách nhau bởi dấu cách.

**Ví dụ**
Input:
```
5
4 5 2 10 8
```
Output:
```
5 10 10 -1 -1
```

**Gợi ý**
Duyệt mảng từ phải sang trái, dùng stack lưu các phần tử ứng viên. Với mỗi phần tử, pop khỏi stack những phần tử nhỏ hơn hoặc bằng nó cho đến khi tìm được phần tử lớn hơn.

**Lời giải**
```cpp
#include <iostream>
#include <stack>
#include <vector>
using namespace std;

int main() {
    int n;
    cin >> n;

    vector<int> arr(n);
    for (int i = 0; i < n; i++) cin >> arr[i];

    vector<int> result(n);
    stack<int> st; // lưu giá trị các phần tử ứng viên

    for (int i = n - 1; i >= 0; i--) {
        // loại bỏ các phần tử nhỏ hơn hoặc bằng arr[i]
        while (!st.empty() && st.top() <= arr[i]) {
            st.pop();
        }
        result[i] = st.empty() ? -1 : st.top();
        st.push(arr[i]);
    }

    for (int i = 0; i < n; i++) {
        cout << result[i];
        if (i < n - 1) cout << " ";
    }
    cout << "\n";
    return 0;
}
```
**Giải thích:** Duyệt từ phải sang trái. Stack lưu các phần tử tiềm năng là "next greater". Với mỗi `arr[i]`, pop tất cả phần tử trong stack nhỏ hơn hoặc bằng `arr[i]` (vì chúng không thể là "next greater" cho `arr[i]` hay các phần tử bên trái). Top của stack sau khi pop chính là next greater element. Độ phức tạp O(N) vì mỗi phần tử chỉ được push/pop một lần.

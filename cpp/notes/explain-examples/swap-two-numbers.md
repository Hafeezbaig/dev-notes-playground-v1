### **Swapping Two Variables – Explained with Buckets**

```cpp
#include <iostream>

int main() {
    int a = 4;
    int b = 5;
    int c = a;
    a = b;
    b = c;
    std::cout << a << b;
    return 0;
}
```

---

### **Concept: Swapping Apples and Oranges**

Imagine you have:

- **Bucket A** with `4 apples`
- **Bucket B** with `5 oranges`

Now, your goal is to **swap** the contents:
- Bucket A should end up with `5 oranges`
- Bucket B should end up with `4 apples`

But we can’t just directly put the oranges in A and apples in B without **losing** one of the original contents.  
So, we use a **third bucket C** to help with the swap:

---

### **Step-by-step with code and analogy**

| Code              | Real World (Buckets)                                     |
|------------------|-----------------------------------------------------------|
| `int a = 4;`      | Bucket A has 4 apples                                     |
| `int b = 5;`      | Bucket B has 5 oranges                                    |
| `int c = a;`      | Take contents of A (apples) and put them in Bucket C     |
| `a = b;`          | Put contents of B (oranges) into Bucket A                |
| `b = c;`          | Put the apples (from Bucket C) into Bucket B             |

---

### **Final Result**

- `a` becomes `5` → A now has oranges  
- `b` becomes `4` → B now has apples  

So the output is:

```cpp
std::cout << a << b;  // prints: 54
```

---


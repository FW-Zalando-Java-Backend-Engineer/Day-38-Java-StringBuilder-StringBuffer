# 📅 Day 38: Java `StringBuilder` & `StringBuffer` — Efficient String Manipulation

---

## 📘 What We Learned Today

Today’s session was all about understanding **mutable strings** in Java using two powerful classes:
- `StringBuilder` (non-thread-safe, fast)
- `StringBuffer` (thread-safe, slightly slower)

We explored **when** to use them, **why** they’re better than `String` in certain scenarios, and **how** to apply them in real code.

---

## ❓ 3 Key Questions

### 🧠 What?
`StringBuilder` and `StringBuffer` are classes for **mutable strings**, meaning you can change their content without creating new objects (unlike `String`, which is immutable).

### 🤔 Why?
- Repeated string modifications with `String` create many intermediate objects → inefficient and memory-heavy.
- `StringBuilder` is best for **single-threaded** performance.
- `StringBuffer` is **thread-safe**, suitable for multi-threaded environments.

### 🛠️ How?
Use their built-in methods like:
- `.append()`
- `.insert()`
- `.deleteCharAt()`
- `.reverse()`
- `.toString()`

These methods allow you to build and modify text efficiently and fluently.

---

## 🛠️ Real-Life Project: **Daily Journal Processor**

### 💡 Scenario:
You’re building a backend feature for a journaling application. Each journal entry can be:
1. **Timestamped** at save time
2. **Reversed** for “mirror” viewing
3. **Uppercased** for emphasis
4. Edited repeatedly, with an **edit counter**

This gave us the perfect playground to compare:
- `StringBuilder` for **speed in single-threaded tasks**
- `StringBuffer` for **safe editing in multi-threaded situations**

---

## 🧩 Classes & Logic

### `JournalEntry.java`
Holds the content and a counter for how many times it's been edited.

### `JournalProcessor.java`
Implements these operations:
| Method                   | Description                              | Type Used       |
|--------------------------|------------------------------------------|------------------|
| `appendTimestamp()`      | Adds current timestamp to the entry      | `StringBuilder`  |
| `reverseContent()`       | Reverses entry content                   | `StringBuffer`   |
| `convertToUpperCase()`   | Converts content to all caps             | `StringBuilder`  |

### `JournalDemo.java`
Shows how each method works step-by-step in a `main()` method.

### `JournalProcessorTest.java`
Uses **JUnit 5** and `@BeforeEach` to test all journal operations individually.

---

## 🧪 Testing Highlights

Each operation is tested for:
- Functional correctness
- Edit count validation
- Expected string transformations

JUnit ensures confidence in our logic with clean, readable tests.

---

## 🎥 Zoom Recording

📹 **[Watch Day 38 Session](https://us06web.zoom.us/rec/share/So5T4kJkcvsvV286DO4M-XuWipbfh_zjWfuwFqWA21fbPk4_f1mAUp7vjnXnvVf_.iigf9UJXEQq8P-BD?startTime=1747124479000)**

---

## 💻 Live Coding & Assignments

- ▶️ [Daily Journal Processor](https://github.com/FW-Zalando-Java-Backend-Engineer/JournalProcessor)
- 🏷️ [Hashtag Formatter](https://github.com/FW-Zalando-Java-Backend-Engineer/Hashtag-Formatter)
- 📢 [Notification Message Builder](https://github.com/FW-Zalando-Java-Backend-Engineer/Notification-Message-Builder)
- 🗃️ [ReportFormatter Utility](https://github.com/FW-Zalando-Java-Backend-Engineer/ReportFormatter-Utility)


---

## 📚 References

- [Baeldung: StringBuilder vs StringBuffer](https://www.baeldung.com/java-string-builder-string-buffer)
- [GeeksForGeeks Comparison](https://www.geeksforgeeks.org/stringbuffer-vs-stringbuilder/)
- [Oracle Docs – StringBuilder](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/StringBuilder.html)

---

## 📌 Final Thought

> “Choose the right tool for the right job.”

If you're dealing with **heavy string operations**, start with `StringBuilder`.  
If you're in a **multi-threaded context**, reach for `StringBuffer`.

Today, you wrote faster, smarter Java — and that’s a big win 🎉


# AWK-scripting
---

## 📌 What is AWK?

**AWK** is a **text-processing and pattern-scanning language** used mainly in:

* Linux / Unix terminals
* Shell scripts
* Log file analysis
* CSV / TSV file processing

Think of AWK as:

> **"A mini programming language for processing text line-by-line"**

AWK works especially well with:

* Columns (fields)
* Rows (records)
* Conditions and actions

---

## 📌 When Should You Use AWK?

Use AWK when you want to:

* Extract specific columns from files
* Filter rows based on conditions
* Perform calculations on data
* Format output

Examples:

* Find students with marks > 80
* Sum a column in a CSV file
* Parse server logs

---

## 📌 How to Start AWK in Terminal

### ✅ Method 1: One-liner AWK Command (Most Common)

```bash
awk 'pattern { action }' filename
```

Example:

```bash
awk '{ print $1 }' data.txt
```

➡️ Prints **first column** of every line.

---

### ✅ Method 2: Interactive Mode (Rarely Used)

```bash
awk
```

Then type AWK code manually (not practical for beginners).

---

### ✅ Method 3: AWK Script File (Professional Way)

Create a script file:

```bash
nano script.awk
```

Add this:

```awk
#!/usr/bin/awk -f
{ print $0 }
```

Make it executable:

```bash
chmod +x script.awk
```

Run it:

```bash
./script.awk data.txt
```

---

## 📌 Understanding AWK Input Model

AWK processes input as:

| Term   | Meaning          |
| ------ | ---------------- |
| Record | One line (row)   |
| Field  | One column       |
| $0     | Entire line      |
| $1, $2 | 1st, 2nd column  |
| NF     | Number of fields |
| NR     | Line number      |

---

## 📌 Basic AWK Structure

```awk
pattern { action }
```

* **pattern** → condition (optional)
* **action** → what to do

If pattern is missing → applies to all lines

---

## 📌 Your First AWK Program

### File: `data.txt`

```
101 Alice 85
102 Bob 72
103 Charlie 90
```

### Print Entire File

```bash
awk '{ print }' data.txt
```

### Print Only Names

```bash
awk '{ print $2 }' data.txt
```

### Print Roll No and Marks

```bash
awk '{ print $1, $3 }' data.txt
```

---

## 📌 Conditions in AWK (if-like)

### Print Students with Marks > 80

```bash
awk '$3 > 80 { print $2 }' data.txt
```

Equivalent to C++ logic:

```cpp
if (marks > 80) print(name);
```

---

## 📌 BEGIN and END Blocks

```awk
BEGIN { print "Start" }
{ print $0 }
END { print "End" }
```

Usage:

```bash
awk 'BEGIN{print "Start"} {print $1} END{print "Done"}' data.txt
```

---

## 📌 Variables in AWK

```bash
awk '{ sum = sum + $3 } END { print sum }' data.txt
```

✔ Variables are auto-declared
✔ No data types required

---

## 📌 Built-in Variables (Very Important)

| Variable | Meaning                |
| -------- | ---------------------- |
| NR       | Record number (line)   |
| NF       | Number of fields       |
| FS       | Field separator        |
| OFS      | Output field separator |

Example:

```bash
awk '{ print NR, NF, $0 }' data.txt
```

---

## 📌 Changing Delimiter (CSV Files)

### CSV File: `marks.csv`

```
101,Alice,85
102,Bob,72
```

```bash
awk -F',' '{ print $2 }' marks.csv
```

---

## 📌 Loops in AWK

```bash
awk '{
  for (i = 1; i <= NF; i++)
    print $i
}' data.txt
```

---

## 📌 If-Else in AWK

```bash
awk '{
  if ($3 >= 80)
    print $2, "Pass"
  else
    print $2, "Fail"
}' data.txt
```

---

## 📌 AWK vs C++ (Quick Comparison)

| C++      | AWK             |
| -------- | --------------- |
| for loop | for loop        |
| if else  | if else         |
| cout     | print           |
| array[i] | array[i]        |
| cin      | automatic input |

---

## 📌 Real-Life Use Cases

* Log file analysis
* System monitoring
* CSV report generation
* Competitive programming input parsing
* Data cleaning pipelines

---

## 📌 Next Topics (Roadmap)

1️⃣ Pattern matching (regex)
2️⃣ Arrays in AWK
3️⃣ Functions
4️⃣ File redirection
5️⃣ AWK + Shell scripting
6️⃣ Real-world projects

---

## ✅ Summary

* AWK is powerful and fast
* Best for text & column-based processing
* Easy if you know C/C++ logic

---

**Kurama 🦊**

> "Once you master AWK, shell scripting becomes 10x powerful."

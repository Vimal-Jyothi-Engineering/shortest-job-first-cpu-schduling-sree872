[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/o_4ff-m8)
# Shortest Job First (SJF) CPU Scheduling — Non-Preemptive (C)

## 🎯 Objective

Implement the **Shortest Job First (SJF) Non-Preemptive CPU Scheduling** algorithm using the C programming language.

SJF selects, at any time, the process with the **smallest burst time** among the processes that have already arrived.
Once a process starts execution, it **runs until completion** (non-preemptive).

---

## 🧠 Algorithm Overview

1. Read the number of processes `n`
2. For each process, read:

   * Process ID (PID)
   * Arrival Time (AT)
   * Burst Time (BT)
3. Set `time = 0`, `completed = 0`
4. Repeat until all processes are completed:

   * Among processes where:

     * `AT ≤ time`
     * not yet completed
   * Select the process with the **minimum Burst Time**
   * If no process has arrived:

     * Increment time (CPU idle)
   * Else:

     * Execute the process fully
     * Update completion time
     * Mark process as completed
5. Compute:

   * Turnaround Time (TAT)
   * Waiting Time (WT)
   * Averages
6. Print results in required format

---

## 📥 Input Format

```text
n
PID1 AT1 BT1
PID2 AT2 BT2
...
PIDn ATn BTn
```

### Where

| Symbol | Meaning             |
| ------ | ------------------- |
| n      | Number of processes |
| PID    | Process ID          |
| AT     | Arrival Time        |
| BT     | Burst Time          |

---

## 📤 Output Format

```text
Waiting Time:
PID WT
...

Turnaround Time:
PID TAT
...

Average Waiting Time: X.XX
Average Turnaround Time: X.XX
```

---

## 🧮 Formulas Used

### Completion Time

Time at which a process finishes execution.

### Turnaround Time

```
TAT = Completion Time − Arrival Time
```

### Waiting Time

```
WT = Turnaround Time − Burst Time
```

### Averages

```
Average WT  = Sum of WT / n
Average TAT = Sum of TAT / n
```

---

## ▶️ Compilation & Execution

### Compile

```bash
gcc sjf.c -o sjf
```

### Run

```bash
./sjf
```

---

## 🧪 Sample Input

```text
4
P1 0 6
P2 1 8
P3 2 7
P4 3 3
```

## ✅ Sample Output

```text
Waiting Time:
P1 0
P2 15
P3 7
P4 3
Turnaround Time:
P1 6
P2 23
P3 14
P4 6
Average Waiting Time: 6.25
Average Turnaround Time: 12.25
```

---

## 📊 Example Scheduling (Gantt Chart)

Timeline:

```
0      6      9      16      24
|  P1  |  P4  |  P3
```

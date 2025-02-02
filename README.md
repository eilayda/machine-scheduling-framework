
# 📌 Machine Scheduling Framework  

## 🔍 Project Overview  
This project provides a **framework for solving scheduling problems** in **single and parallel machines**. It includes **dispatching rules, scheduling algorithms, and visualization tools** to evaluate scheduling objectives and optimize job sequences using **meta-heuristics**.  

### 🚀 Features  
✔ **Single Machine Scheduling:** Supports various scheduling objectives such as **makespan, total completion time, total tardiness, weighted completion time, and maximum lateness**.  
✔ **Gantt Chart Visualization:** Generates Gantt charts to visualize scheduling results.  
✔ **Dispatching Rules Application:** Implements rules like **Shortest Processing Time (SPT), Earliest Due Date (EDD), Longest Processing Time (LPT), and more**.  
✔ **Parallel Machine Scheduling:** Extends scheduling capabilities to **multiple machines**, supporting different job allocation strategies.  
✔ **Meta-Heuristic Optimization:** Implements **local search** techniques to improve schedules.  

---

## 📂 Project Structure  
```plaintext
├── ie_439_project.ipynb       # Main implementation script  
├── input_439.xlsx          # Input dataset (jobs data)  
├── Project steps.docx      # Detailed project steps  
├── Machine Scheduling Project Report.pdf  # Final project report  
└── README.md               # This file  
```

---

## 📊 How It Works  
### 1️⃣ **Single Machine Scheduling**  
- **Define objectives:** Choose from **makespan, total completion time, tardiness, etc.**  
- **Input job sequence:** Provide job details (processing time, due date, weight).  
- **Compute completion times** and evaluate scheduling performance.  

### 2️⃣ **Gantt Chart Generator**  
- Visualizes job schedules for easy analysis.  
- Supports **custom job sequences**.  

### 3️⃣ **Dispatching Rules Application**  
- Implements various **priority-based job scheduling strategies**.  
- Automatically evaluates **performance metrics** for different rules.  

### 4️⃣ **Parallel Machine Scheduling**  
- Assigns jobs to **multiple machines** using predefined rules (**SPT, LPT, Wrap-Around**).  
- Evaluates **machine workload distribution**.  

### 5️⃣ **Meta-Heuristic Optimization**  
- **Local Search Strategies:** Adjusts job sequences to improve schedule efficiency.  
- **Optimization Metrics:** Reduces makespan, lateness, or weighted tardiness.  

---

## 📌 Example Usage  
To evaluate scheduling objectives for a given job sequence:  
```python
scheduler = SingleMachineScheduler(df)
scheduler.evaluate_objective("M")  # Calculates makespan
```

To apply a **dispatching rule**:  
```python
sorted_df = spt(df)  # Shortest Processing Time (SPT) rule
create_gantt(sorted_df, title="Gantt Chart - SPT")
```

To generate a **Gantt Chart** for a custom job sequence:  
```python
generate_gantt_chart(scheduler, sequence=[3,2,1,4])
```

To run the **Parallel Machine Scheduler**:  
```python
scheduler = ParallelMachineScheduler(df, num_machines=3)
scheduler.assign_jobs(rule="SPT")
scheduler.generate_gantt_chart()

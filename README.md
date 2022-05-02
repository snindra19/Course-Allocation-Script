# **Student Elective Allocation System**

This project automates the process of allocating students to elective subjects based on their preferences and seat capacity constraints. It also generates reports for allocated and unallocated students and visualizes the allocation distribution.

---

## **Features**
- Reads student choices and subject constraints from CSV files.  
- Allocates students to subjects in order of their preferences and seat availability.  
- Handles underfilled electives by removing them and reallocating affected students.  
- Generates output files:
  - `allocations.csv` → Final allocation list
  - `unallocated.csv` → Students who could not be allocated (if any)
- Provides an **interactive search** to check the subject allocated for a specific student.  
- Displays **pie chart and bar chart** showing allocation distribution based on choices.  

---

## **Input Files**
1. **students.csv**  
   - Must contain columns: `USN`, `Name`, `Timestamp`, and `Choice1`, `Choice2`, ...  
   - Example:
     ```
     USN,Name,Timestamp,Choice1,Choice2,Choice3
     1RV20CS001,John Doe,2025-04-01 10:30:00,AI,ML,Cloud
     1RV20CS002,Jane Smith,2025-04-01 10:35:00,ML,AI,Cloud
     ```

2. **constraints.csv**  
   - Must contain columns: `Subject`, `MinCapacity`, `MaxCapacity`  
   - Example:
     ```
     Subject,MinCapacity,MaxCapacity
     AI,5,10
     ML,5,10
     Cloud,5,10
     ```

---

## **Installation**
1. Install Python (3.8 or above)  
2. Install required libraries:
   ```bash
   pip install pandas plotly

## **Usage**
1. Place students.csv and constraints.csv in the same directory as the script.
2. Run the script: python allocation.py
3. Outputs:
    - allocations.csv is generated with all allocations.
    - unallocated.csv is generated if some students could not be allocated.
    - Interactive charts (pie & bar chart) display in the browser.
4. You can search for a student's allocation by entering their USN when prompted:
    - Enter a USN to find allocated subject (or type 'exit' to quit'): 1RV20CS001 
    - USN: 1RV20CS001 → Subject: AI

---

## **Visualization**
1. Pie Chart: Percentage of students allocated by their choice number.
2. Bar Chart: Number of students allocated for each choice.

---

## **Notes**
1. Students are allocated based on timestamp order (earlier submissions have higher priority).
2. If a subject has fewer students than its minimum capacity, it is removed, and students are reallocated.
3. Visualization uses Plotly, so interactive charts will open in the default browser.

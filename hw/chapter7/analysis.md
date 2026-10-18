
# OSTEP Chapter 7: CPU Scheduling Analysis

## Q1: FIFO vs. SJF

- **Prediction**: FIFO will have a high turnaround time due to the Convoy Effect. SJF will have a shorter turnaround time but may starve long jobs.
- **Reasoning**: FIFO forces short jobs to wait behind long ones. SJF optimizes turnaround time by clearing short jobs first.
- **Verified Results** (Seed: 1234, Jobs: 100,200,300):
  - **FIFO**:
    - Avg Response Time = `...` *(Replace with your number)*
    - Avg Turnaround Time = `...` *(Replace with your number)*
  - **SJF**:
    - Avg Response Time = `...` *(Replace with your number)*
    - Avg Turnaround Time = `...` *(Replace with your number)*
- **Conclusion**: SJF has a better average turnaround time, but FIFO provides a more predictable (though poor) response time.

## Q3: Round-Robin with Different Quantum

- **Prediction**: A smaller quantum will improve response time but worsen turnaround time due to frequent context switches. A larger quantum approaches FIFO behavior.
- **Verified Results**:
  - **RR (q=10)**:
    - Avg Response Time = `...` *(Replace with your number)*
    - Avg Turnaround Time = `...` *(Replace with your number)*
  - **RR (q=50)**:
    - Avg Response Time = `...` *(Replace with your number)*
    - Avg Turnaround Time = `...` *(Replace with your number)*
- **Conclusion**: The quantum size must balance interactive responsiveness and overall system throughput.

## Q4 & Q5: Quantum Size Effects

- **Observation**: When quantum is extremely small, context switch overhead dominates. When quantum is extremely large, it degenerates into FIFO. 
- **Result**: There is a sweet spot for quantum size to balance response time and turnaround time.

## Q6 & Q7: Convoy Effect & Formula

- **Convoy Effect**: Workload `500,10,10,10,10`. Under FIFO, the short jobs wait for the 500-length job, causing massive delays. SJF solves this.
- **Formula (FIFO)**: \(T_{turnaround, i} = \sum_{k=1}^{i} T_{run, k} - T_{arrival, i}\)
  *(Turnaround time depends on the sum of all previous job lengths.)*

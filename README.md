## Size of the Work Unit for Optimal Performance

The size of the work unit, which refers to the number of sub-problems a worker receives in a single request from the boss, was determined to optimize performance based on empirical analysis and performance testing.

### Optimal Work Unit Size

For the given implementation, the work unit size is determined as follows:

- **For \( n \leq 500 \)**: The work unit size is set to \( n \), meaning each worker handles all tasks within a single request. This approach simplifies the distribution of tasks and minimizes the overhead associated with managing multiple requests.

- **For \( n > 500 \)**: The work unit size is set to the ceiling of the square root of \( n \), calculated using the `MathUtils.ceil` function. Specifically, the chunk size is \( \text{ceil}(\sqrt{n}) \), which balances the workload across workers and optimizes performance by ensuring that each worker processes a manageable number of tasks. This approach effectively distributes the total workload while keeping task management overhead low.

### Rationale for Work Unit Size

The choice of work unit size was influenced by the need to balance the following factors:

- **Parallelism**: Larger work units can reduce the overhead associated with task management and inter-worker communication, leading to better parallelism and performance.

- **Task Management Overhead**: If the work unit size is too large, the tasks become unwieldy, and if it is too small, the overhead of managing numerous requests increases. The selected size aims to strike a balance between these extremes.

The optimal work unit size was determined through performance testing, where different sizes were evaluated to identify the configuration that yielded the best performance in terms of both execution speed and efficient use of resources. The empirical results confirmed that using the ceiling of the square root of \( n \) for work unit size provided the best overall performance for our implementation.

## Result of Running the Program

### Input
The program was run with the following input: ./Pony 1000000 4 

### Output
The output of the program for the given input was: There are no numbers following Lukas' theorem within the specified range.

## Running Time and Parallelism Analysis

### Interpretation
- **User Time:** 0.41 seconds
- **System Time:** 0.02 seconds
- **CPU Usage:** 758%
- **Total Time:** 0.056 seconds

The high ratio of CPU time to real time indicates effective utilization of multiple cores, reflecting strong parallelism in the computation.


## Largest Problem Solved

The largest problem size that I was able to solve with the current implementation was: lukas 1000000000 24 



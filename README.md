
# **Concurrent Binary Search Tree with Various Locks**
This project implements a concurrent binary search tree (ConBST) that utilizes logical ordering for synchronization and evaluates its performance using different locking mechanisms under varying thread counts.

## **Introduction**
The concurrent binary search tree aims to provide a thread-safe data structure that supports efficient insertion, deletion, and search operations in a concurrent environment. This project explores the performance of ConBST by employing various locking mechanisms commonly used in concurrent programming.

### **Implemented Locks**
The following locking mechanisms have been implemented and evaluated for their impact on ConBST's performance:

### **Test And Set Lock**
- A basic lock that uses atomic operations for mutual exclusion. Threads repeatedly try to acquire the lock until successful, leading to potential contention.

### **Test Test And Set Lock**
- Similar to the Test And Set Lock but with additional spinning on a local flag before attempting to acquire the lock, reducing contention in some scenarios.

### **Test Test And Set Lock with Backoff**
- Enhancement to the Test Test And Set Lock, introducing a backoff strategy where a thread yields its execution for a brief period when unable to acquire the lock immediately.

### **Array-Based Queue Lock**
- A lock implementation that uses an array-based queue for thread synchronization. It aims to minimize contention by allowing threads to wait in a queue.

### **CLH Queue Lock**
- A queue-based lock utilizing the Craig, Landin, and Hagersten (CLH) lock algorithm. It employs a linked list of nodes to manage thread contention.

### **MCS Queue Lock**
- Another queue-based lock implementing the Mellor-Crummey and Scott (MCS) lock algorithm. Threads maintain a queue structure to handle contention for access.

## Usage
To utilize the implemented locks with the ConBST, follow these steps:

- **Compilation**: Compile the project using a Java compiler (e.g., javac).<br />
- **Lock Selection**: Modify the ConBST_Test.java source code to select the desired lock for testing by uncommenting the respective lock.<br />
- **Running Tests**: Run the ConBST_Test program with varying thread counts (1, 2, 4, 6, 8, 10, 12, 14, and 16) to evaluate the lock's performance.<br />
- **Performance Testing**: The ConBST_Test program facilitates performance testing under different thread counts. Observe the throughput and efficiency of each lock under varying concurrent scenarios.

## Results
The test results provide insights into the behavior of each locking mechanism concerning scalability, contention, and overall performance. Analysis of these results can help identify the suitability of locks for different workload types and thread counts.

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/d1003b00-fb55-4186-9b48-abde1d09daa2)

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/44bd0a61-bdf0-4455-bee3-e5a30b03c4fe)

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/39a6ef87-df35-4271-94a1-1cc2ac72cb56)

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/dd604163-78c0-4de2-a637-327f34d39c2c)

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/8a3c5e5a-a2cd-42c6-b8d7-265f80ac6222)

![image](https://github.com/harshakarnam57/HPC3/assets/64098766/2fdce187-c308-4927-b04f-1d4a109e0085)

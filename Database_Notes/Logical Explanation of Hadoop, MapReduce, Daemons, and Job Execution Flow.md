
Hadoop is a **distributed computing framework** designed to process large volumes of data across multiple machines. It works by dividing tasks into smaller units and executing them in parallel, while efficiently managing memory, processes, and permissions.

---

## 1. Hadoop as a Protocol-Driven System

Hadoop does not work as a single program. Instead, it is a **protocol-based distributed system**.

- Communication between components happens through **well-defined protocols**
    
- These protocols ensure:
    
    - Data consistency
        
    - Fault tolerance
        
    - Controlled access
        

Because Hadoop runs across many machines, strict protocol rules are required to coordinate actions between nodes.

---

## 2. Multiple Background Processes (Daemons)

Hadoop relies heavily on **background services (daemons)** that continuously run in the system.

These daemons manage:

- Storage
    
- Job scheduling
    
- Resource allocation
    
- Monitoring and recovery
    

Examples include:

- NameNode
    
- DataNode
    
- ResourceManager
    
- NodeManager
    

These processes consume memory and CPU but are essential for smooth cluster operation.

---

## 3. MapReduce as a Set of Background Programs

MapReduce is not a single execution unit. It is a **collection of coordinated background programs**.

MapReduce consists of:

- **Mapper tasks** – process input data
    
- **Reducer tasks** – aggregate results
    
- **Shuffle and Sort** – intermediate data transfer
    

All these components run as **separate processes**, coordinated by the cluster manager.

---

## 4. Planning Phase (Job Submission)

When a user submits a job:

1. The job enters the **planning phase**
    
2. Hadoop analyzes:
    
    - Input data size
        
    - Number of blocks
        
    - Resource requirements
        
3. The job is divided into smaller tasks
    

This phase ensures efficient parallel execution.

---

## 5. Listener and Server Process

Once planning is complete:

- A **listener process** waits for incoming job requests
    
- The **server process** (ResourceManager / JobTracker) receives the job
    

This server:

- Accepts the request
    
- Registers the job
    
- Initiates validation
    

---

## 6. Public World vs Private World (Security Model)

Hadoop distinguishes between:

- **Public world** → user-submitted jobs
    
- **Private world** → internal system operations
    

Before execution:

- The job transitions from public space to private execution space
    
- This prevents unauthorized interference
    

---

## 7. Permission Checking

Before execution, Hadoop performs **permission checks**:

- User authentication
    
- File access permissions
    
- Execution rights
    

This ensures:

- Data security
    
- Controlled resource usage
    
- Multi-user safety in shared clusters
    

If permissions fail, execution is denied.

---

## 8. Execution Phase

After permission approval:

- The job is executed across cluster nodes
    
- Mapper and Reducer tasks run in parallel
    
- Intermediate results are transferred and combined
    

Execution is monitored continuously by background daemons.

---

## 9. Program Completion and Result Return

Once execution finishes:

- Results are stored (usually in HDFS)
    
- Status is returned to the user
    
- Resources are released
    

This marks the completion of the MapReduce job lifecycle.

---

## Conclusion

The notes collectively describe how **Hadoop operates as a protocol-based distributed system**, relying on **multiple background processes** to manage memory, security, and execution. MapReduce jobs follow a structured flow—from planning and permission checking to execution—ensuring scalability, efficiency, and safety in large-scale data processing.
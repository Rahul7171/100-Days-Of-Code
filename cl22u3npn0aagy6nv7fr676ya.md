## Election algorithm and distributed processing

**Distributed Algorithm:**

*   The term “distributed algorithm” refers to an algorithm that runs across a network.
*   Each CPU has its own memory and communicates with other processors via networks.
*   A process on one machine communicates with a circle on another device in a network.
*   Many distributed system methods necessitate the usage of a coordinator to fulfill functions required by other system processes.  
    To select a coordinator, election algorithms are used.

**Election Algorithms:**

*   Election algorithms choose a process from a group of processors to act as a coordinator.
*   The election algorithm determines where a new copy of the coordinator should be restarted.
*   The election algorithm assumes that every active process in the system has a unique priority number.
*   The process with the highest priority will be chosen as a new coordinator.  
    Then this number is sent to every active process in the distributed system.

**We have two election algorithms for two different configurations of a distributed system.**

1.  **The Bully Algorithm –**

*   An algorithm applies to the system where every process can send a message to every other process in the system.
*   Algorithm — Suppose process P sends a message to the coordinator.  
    Now, process P sends an election message to every process with a high priority number.
*   Then it sends a message to all lower priority number processes that it is elected as their new coordinator.
*   However, if an answer is received within time T from any other process Q,(I) Process P again waits for time interval T’ to receive another message from Q that it has been elected as coordinator. (II) If Q doesn’t respond within time interval T’ then it is assumed to have failed and the algorithm is restarted.

**2\. The Ring Algorithm –**  
This algorithm applies to systems organized as a ring(logically or physically). In this algorithm, we assume that the link between the process is unidirectional and every process can message to the process on its right only. A data structure that this algorithm uses is the **active list**, a list that has the priority number of all active processes in the system.

**Algorithm –**

1.  If process P1 detects a coordinator failure, it creates a new active list that is empty initially. It sends an election message to its neighbor on right and adds number 1 to its active list.
2.  If process P2 receives message elected from processes on left, it responds in 3 ways:

*   (I) If the message received does not contain 1 inactive list then P1 adds 2 to its active list and forwards the message.
*   (II) If this is the first election message it has received or sent, P1 creates a new active list with numbers 1 and 2. It then sends election message 1 followed by 2.
*   (III) If Process P1 receives its own election message 1 then the active list for P1 now contains numbers of all the active processes in the system. Now Process P1 detects the highest priority number from the list and elects it as the new coordinator.
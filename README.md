# Proposal
## Motivation:
As someone with experience in the healthcare field, I’ve witnessed the challenges of scheduling surgeries in large hospitals, especially those with multiple operating rooms. In emergency situations, surgeries need to be prioritized quickly to ensure the right patients receive care in a timely manner. Elective surgeries, while important, have more flexibility in timing. The problem of prioritizing surgeries based on their urgency and available operating rooms is something that hospitals face daily. This project explores how a priority queue can be used to efficiently schedule surgeries, ensuring that the most urgent cases are handled first and operating rooms are managed effectively.

## Data Structures and Algorithms:
To address this scheduling problem, I will implement a priority queue that is a data structure that allows the efficient insertion and removal of elements based on priority. In the context of this project, each surgery will be assigned a priority (e.g., High, Medium, Low) and the queue will automatically ensure that the most urgent surgeries are scheduled first and be able to continue going through the quue until all rooms have been asigned.

The challenge in this problem is scheduling surgeries while managing multiple operating rooms and considering both the priority of surgeries and their duration. The priority queue will allow us to organize surgeries based on priorty, while additional logic will handle room assignments and surgery durations.

## Priority Queue Implementation:

Surgery Class: Each surgery will have a priority level (e.g., Emergent, High, Medium, Low), a patient name, and a surgery duration.
PriorityQueue Class: This class will manage the heap structure of the priority queue, ensuring that surgeries are always arranged by their priority.
The MHPUp and MHPDown functions will maintain the heap property of the priority queue, ensuring that the highest priority surgery is always scheduled next.
Scheduler Class: This class will simulate a hospital environment, managing multiple operating rooms and scheduling surgeries based on room availability and the priority of each surgery.
Motivation for Using a Priority Queue:
Priority queues are particularly well-suited for this problem because they allow for efficient retrieval of the highest-priority surgery, ensuring that the most urgent procedures are handled first. A heap-based priority queue provides O(log n) time complexity for insertion and removal of surgeries, which is efficient enough for handling a reasonable number of surgeries in a hospital setting.

Additionally, the priority queue can help us manage the complexity of scheduling surgeries across multiple operating rooms. For example, if a room becomes available, the priority queue ensures that the next highest priority surgery is scheduled without needing to manually search for the next surgery to schedule.

Technical Hurdles:
One technical challenge I faced was ensuring that the heap property of the priority queue is always maintained when surgeries are added or removed. I solved this by using two functions, MHPUp and MHPDown, which restore the heap property after a surgery is inserted or removed. This is crucial because the priority queue needs to remain sorted at all times to guarantee that the highest priority surgery is processed next.

Another hurdle was managing room availability in parallel with surgery scheduling. Since surgeries have different durations, it's important to track when each room will be free to schedule the next surgery. I implemented this logic by keeping an array of room availability times, which are updated whenever a surgery is scheduled.

# Pseudocode

### How the System Works:
```
- Step 1: The system initializes with multiple operating rooms and a priority queue of surgeries.
- Step 2: Surgeries are added to the priority queue based on their priority and duration.
- Step 3: The scheduler begins assigning surgeries to available rooms, and prints out the schedule.
- Step 4: If a room is available, the surgery is scheduled. If no rooms are available, the surgery will be postponed until a room is free.
- Step 5: printing schedule to visbly see results and to help see issues with code 
```

### Surgery Class
```
Define a Surgery class with the following attributes:
Name of the patient
Type of surgery 
Priority of the surgery 
Duration of the surgery 

```

### Define a PriorityQueue class to manage surgeries in a heap (priority queue):
```
USING A HEAP
From the textbook using the heap and queue readings: 
- MHPUp function: (Move the surgery up in the heap)
While the node is not at the top:
Compare the priority of the current surgery with its parent's priority
If the current surgery has a higher priority than its parent:
Swap the current surgery with its parent
Move the node to the parent's position
Otherwise, stop the process
- MHPDown function: (Move the surgery down in the heap)
Set the child index to the left child of the current node
While the node has a child:
Compare the priority of the current surgery with its children
If one of the children has a higher priority:
Swap the current surgery with the child having the higher priority
Move the node to the child’s position

Scheduler Class
```

 ### Define a Scheduler class to handle the scheduling of surgeries in multiple rooms:
 ```
 Number of available operating rooms
 A list to track when each room will be free
 A priority queue of surgeries to be scheduled

While there are surgeries in the queue:
Get the surgery with the highest priority from the queue

For each room:
Check if the room is available 
If the room is available:
Assign the surgery to the room
Update the room's availability time

Print the surgery details (patient name, room number, scheduled time)
Break the loop to schedule the next surgery

Repeat until all surgeries are scheduled and queue is empty
```





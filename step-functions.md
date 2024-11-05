### Step Functions
Step functions are used to create workflows consist of multiple services to automate processes.
Step functions are based on *state machines* and *tasks*. State machines are the workflows. Each step in workflow is called *state*.
Each time a state machine is executed performing tasks, it is reffered as *execution*.

**Flow:** Refers to execution flow of states within state machine. These could be choice (if-else), pass (transforms data or act as placeholder), wait (delays for a specified time).

**Actions:** Actions basically refer to tasks that a state within a state machine can perform. For example, invoking a lambda function is an action.

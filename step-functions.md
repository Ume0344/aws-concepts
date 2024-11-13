### Step Functions
Step functions are used to create workflows consist of multiple services to automate processes.
Step functions are based on *state machines* and *tasks*. State machines are the workflows. Each step in workflow is called *state*.
Each time a state machine is executed performing tasks, it is reffered as *execution*.

**Flow:** Refers to execution flow of states within state machine. These could be choice (if-else), pass (transforms data or act as placeholder), wait (delays for a specified time).

**Actions:** Actions basically refer to tasks that a state within a state machine can perform. For example, invoking a lambda function is an action.

### InputPath, Parameters, ResultSelector
These fields can be used to manipulate json as it moves through the workflow.

#### InputPath:
It is used to select a portion of the state input. i.e, the following input is given to state
```
{   
    "teacher": "pqr"
    "student1": {
        "name": "xyz",
        "age": "123",
        "class": "abc"
    }
}
```
`"InputPath": "$.student1"` , using this, following will be passed as an input to next step/state;
```
{
    "name": "xyz",
    "age": "123",
    "class": "abc"
}
```

#### Parameters
Using Parameters, we can pass collection of key-value pairs as a JSON. i.e,
```
Parameters: {
    "studentID": "1",
    "studentDetails":{
        "name": "$.student1.name", 
        "age": "$.student1.age",
        "class": "$.student1.class"
    }
}
```
Parameters would be passed as;
```
Parameters: {
    "studentID": "1",
    "studentDetails":{
        "name": "xyz", 
        "age": "123",
        "class": "abc"
    }
}
```

#### ResultSelector
It is used to manipulate state's result before `ResultPath` is applied. Using `ResultSelector`, we can define what part of state results we want to pass to `ResultPath`.

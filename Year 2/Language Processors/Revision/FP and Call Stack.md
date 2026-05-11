**The Basics**

When a function is called, the program needs somewhere to store the following
- The parameters passed in
- The functions local variables
- The return address (where to jump back to when the function is finished)
- The previous FP value

All of this is stored in a **stack frame**, pushed onto the call stack

**Frame Pointer**

This points to a fixed position within the current frame. Parameters and locals are accessed as offsets from FP. 

```
FP + 4 = Parameter 1
FP + 8 = Parameter 2
FP - 4 = Local Variable 1
FP - 8 = Local Variable 2
```


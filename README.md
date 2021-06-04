# General GDB workflow
Set disassembler flavor to Intel.
```
set disassembly-flavor intel 
```
Look at main function to get an overview and create a control graph.
```
disassemble main
```
Set a break point in main before running the program. A break point is a point where the execution stops.
```
break *main
run
```
Look at the registers
```
info registers
```
Step into main e.g. get to be able to step through the addresses in main.
```
si
```
Go to the next instructions in order to follow the addresses from the control graph, or what you observed in main.
```
ni
```
We use ```ni``` here to step over/through function calls, while si would step into the function calls. This way we can follow the main function and not follow stuff like ```puts``` i.e. 
The command can be repeated by hitting enter. 

Depending on what we are debugging we might want to set break points at other addresses, before running the program again with user input. We might have located them in our control graph.
```
break *<some address>
run
```
Go forward to the next break point. ```continue``` will run the program until the next break point.
```
continue
```
Check the reigsters at this break point.
```
info registers
```

# DISTek U 201 Mentee

Jeff G., assigned mentor, teaching Simulink basics.

Project.slx contains completed assignments.

This project was implemented in MATLAB R2024a.


## Assignment 1

Create a MATLAB function block within a subsystem that will take data from a temperature sensor (**TSnsrT** via a simulated Signal Editor block) and control three Boolean signals (**TLow**, **TMid**, and **THi**) according to the following logic:

1. If **TSnsrT** is equal to 100 deg C or lower, then **TLow** shall output high and **TMid**/**THi** shall output low.

2. If **TSnsrT** is higher than 100 deg C and lower than or equal to 200 deg C, then **TMid** shall output high and **TLow**/**THi** shall output low.

3. If **TSnsrT** is higher than 200 deg C, then **THi** shall output high and **TLow**/**TMid** shall output low.

## Assignment 2

Create a MATLAB action language type state flow chart that takes input signals from Signal Editor (**PSnsrP**: double and **PSnsrFltd**: Boolean) and outputs Boolean signals **PSnsrFltd**, **PHi**, **PMid**, and **PLo** with the following logic:

1. If **PSnsrP** is any value and **PSnsrFltd** is high, then **PHi**/**PMid**/**PLo** shall output low and **PSnsrFltd** shall output high.

2. If **PSnsrP** is less than or equal to 100 kPa and **PSnsrFltd** is low, then **PLo** shall output high and **PHi**/**PMid**/**PSnsrFltd** shall output low.

3. If **PSnsrP** is greater than 100 kPa and less than 200 kPa and **PSnsrFltd** is low, then **PMid** shall output high and **PHi**/**PLo**/**PSnsrFltd** shall output low.

4. If **PSnsrP** is greater than 200 kPa and **PSnsrFltd** is low, then **PHi** shall output high and **PMid**/**PLo**/**PSnsrFltd** shall output low.

## Assignment 3

Create a state flow component that uses a state machine to control a sensor with a feedback loop:

Input Signals:

**CmdInput** (Boolean)

**FltdInput** (Boolean)

**DataInput** (Double)

Output Signals:

**CmdOutput** (Boolean)

**FltdOutput** (Boolean)

**DataOutput** (Double)

1. If **CmdInput** is high and **FltdInput** is low, then this machine shall pass through the **DataInput** value to **DataOutput**, **CmdInput** to **CmdOutput**, and **FltdInput** to **FltdOutput**.

2. If **CmdInput** is low and **FltdInput** is low, then the machine shall pass through **DataInput** = 0, **CmdOutput** as low, and **FltdOutput** as low.

3. If **CmdInput** is low and **FltdInput** is high, then it shall pass through **DataInput** = 0, **CmdOutput** as low, and **FltdOutput** as low (i.e. do nothing).

4. If **CmdInput** is high and **FltdInput** is high, then this machin shall act as a lash. It shall output **CmdOutput** as low, **FltdOutput** as high, and **DataOutput** as 0 until such a time that **CmdInput** signal cycles from high, to low (same output as step 3), to high again (reset). If the fault is cleared after reset, the machine will perform the same as in step 1. If not, then it will re-enter the latched faulted state.

## Assignment 4

TBD
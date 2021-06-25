# MIPS-CPU-Multicycle-Info
A brief introduction of multicycle-MIPS-CPU54 for Tongji University CSers 

### 难点

- 多周期的状态设计涉及到时序逻辑，组合逻辑控制器设计比较复杂

- 中间变量值的存储。

- div、divu指令控制。

- 中断指令。

### 坑：

- MIPS246网站上多周期CPU54的tb是在pc改变时输出pc，instr和32个寄存器的值，以避免不同CPU设计的周期不同带来测试的不便，**因此一条指令只能改变一次pc，并且pc的改变必须在Regfile的内容改变之后。**

- 教材《数字逻辑与组成原理实践教程》上关于MIPS54条指令的描述与MIPS246上的pdf文件有不同的地方：**教材上是MULT指令，而pdf文件上是MUL指令**，这两条指令无论是指令格式还是执行流程，差别都很大，并且mul指令和clz指令的opcode一样。**提交的coe文件使用的是MUL而非MULT**。

- 3条中断指令结束后要进入异常程序入口（0x4）,**即中断指令执行完毕后要将PC改为0x00400000**。

- 多周期CPU54采用的测试coe文件是：mips_54_mars_simulate_student_ForWeb.coe，还有一份名字类似的文件是：mips_54_mars_simulate_student.coe，不要用错

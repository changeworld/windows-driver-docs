---
title: "ph (Step to Next Branching Instruction)"
description: "The ph command executes the program until any kind of branching instruction is reached, including conditional or unconditional branches, calls, returns, and system calls."
keywords: ["ph (Step to Next Branching Instruction) Windows Debugging"]
ms.date: 05/23/2017
topic_type:
- apiref
ms.topic: reference
api_name:
- ph (Step to Next Branching Instruction)
api_type:
- NA
---

# ph (Step to Next Branching Instruction)


The **ph** command executes the program until any kind of branching instruction is reached, including conditional or unconditional branches, calls, returns, and system calls.

User-Mode

```dbgcmd
[~Thread] ph [r] [= StartAddress] [Count] 
```

Kernel-Mode

```dbgcmd
ph [r] [= StartAddress] [Count] 
```

## Parameters


<span id="_______Thread______"></span><span id="_______thread______"></span><span id="_______THREAD______"></span> *Thread*   
Specifies threads to continue executing. All other threads are frozen. For more information about the syntax, see [Thread Syntax](thread-syntax.md). You can specify threads only in user mode.

<span id="_______r______"></span><span id="_______R______"></span> **r**   
Turns on and off the display of registers and flags. By default, the registers and flags are displayed. You can disable register display by using the **phr**, [**pr**](p--step-.md), [**tr**](t--trace-.md), or .prompt\_allow -reg commands. All of these commands control the same setting and you can use any of them to override any previous use of these commands.

You can also disable register display by using the l-os command. This setting is separate from the other three commands. To control which registers and flags are displayed, use the [**rm (Register Mask)**](rm--register-mask-.md) command.

<span id="_______StartAddress______"></span><span id="_______startaddress______"></span><span id="_______STARTADDRESS______"></span> *StartAddress*   
Specifies the address where the debugger begins execution. Otherwise, the debugger begins at the instruction that the instruction pointer points to. For more information about the syntax, see [Address and Address Range Syntax](address-and-address-range-syntax.md).

<span id="_______Count______"></span><span id="_______count______"></span><span id="_______COUNT______"></span> *Count*   
Specifies the number of branching instructions that must be encountered for this command to stop. The default value is one.

## Environment

|  Item       | Description               |
|-----------|------------------------|
| Modes     | user mode, kernel mode |
| Targets   | live debugging only    |
| Platforms | all                    |

 

## Additional Information

For more information about related commands, see [Controlling the Target](../debugger/controlling-the-target.md).

## Remarks

The **ph** command causes the target to begin executing. This execution continues until a branching instruction is reached or a breakpoint is encountered.

If the program counter is already on a branching instruction, the entire branching instruction is executed. After this branching instruction is returned, execution continues until another branching instruction is reached. This execution, rather than tracing, of the call is the only difference between **ph** and [**th (Trace to Next Branching Instruction)**](th--trace-to-next-branching-instruction-.md).

In source mode, you can associate one source line with multiple assembly instructions. The **ph** command does not stop at a branching instruction that is associated with the current source line.


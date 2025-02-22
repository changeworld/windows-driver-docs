---
title: Security During User-Mode Debugging
description: Security During User-Mode Debugging
keywords: ["security considerations, user-mode debugging"]
ms.date: 11/26/2017
---

# Security During User-Mode Debugging

When a user-mode debugger is active, it can effectively control any of the processes on the computer.

There are at least three possible ways in which security problems could arise during user-mode debugging:

-   If you use corrupt or destructive extension DLLs, they could cause your debugger to take unexpected actions, possibly affecting applications other than your target.

-   It is possible that corrupt or destructive symbol files could also cause your debugger to take unexpected actions, possibly affecting applications other than your target.

-   If you are running a remote debugging session, an unexpected client might attempt to link to your server. Or perhaps the client you are expecting might attempt to perform actions that you do not anticipate.

For suggestions on how to guard against unexpected remote connections, see [Security During Remote Debugging](security-during-remote-debugging.md). After a remote client has joined a user-mode debugging session, there is no way to restrict its access to processes on your computer.

If you are not performing remote debugging, you should still beware of bad symbol files and extension DLLs. Do not load symbols or extensions that you distrust.
 
## See also

[Security During Kernel-Mode Debugging](security-during-kernel-mode-debugging.md)

[Security During Remote Debugging](security-during-remote-debugging.md)
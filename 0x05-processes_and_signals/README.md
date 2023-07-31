The process init is the only process that will always have the same PID on any session and on any system, and that PID is 1. This is because init is always the first process on the system and is the ancestor of all other processes.
<br>

A very large PID does not necessarily mean that there are anywhere near that many processes on a system. This is because such numbers are often a result of the fact that PIDs are not immediately reused, in order to prevent possible errors.
<br>
The default maximum value of PIDs is 32,767. This maximum is important because it is essentially the maximum number of processes that can exist simultaneously on a system. Although this will almost always be sufficient for a small system, large servers may require many more processes. The lower the maximum value, the sooner the values will wrap around, meaning that lower values do not necessarily indicate processes that started to run earlier.
<br>
The file pid_max, which was introduced with the Linux 2.5 kernel, specifies the value at which PIDs wrap around (i.e., the value in this file is one greater than the maximum PID). It has a default of 32768, but it can be set to any number up to approximately four million. The maximum number of processes on a system is only limited by the amount of physical memory (i.e., RAM) available.

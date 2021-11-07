# Process_01

In this session, we will learn about the overall operating principles of hardware.

We call ssd or hdd storage, and ram is called memory, and cpu is called processor. Let's compare storage and memory among these.

Storage is inexpensive and has a large capacity while computers are slow to read and write. Conversely, memory is very fast but expensive and small in capacity.

At this time, since storage cannot keep up with the processor's speed, the computer operates by loading files in storage into memory when they are executed.

Think about it. We have seen earlier that the commands we used, such as mkdir, top, and rm, exist in file form in the /bin or /sbin directory. That is, **these commands are stored in storage and are programs.** If we operate these commands on the terminal, it is executed as each program is loaded from the storage device to the memory. **The executed program is called a 'process'** and ultimately executes the program through the process of processing programs loaded in memory, that is, processes, by the processor.


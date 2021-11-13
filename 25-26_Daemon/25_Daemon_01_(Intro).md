# Daemon_01

Take an example to understand what __Daemon__ is. If you take a look around my house, you will be able to see many home appliances. At this time, it can be divided into products that are always turned on and products that are turned on only when used, for example, refrigerators and electronic door locks will always be turned on, and microwave ovens, washing machines, and TVs will only be turned on when used.

The same goes for programs. There are programs that run all the time and programs that run only when used. Commands we have learned so far, such as __ls, rm, and mkdir__, are programs that only turn on when executed.

So, what are some programs that are running all the time? We call it __daemon__ and will find out about it.

## Client & Server

Suppose we access the web. For example, if you connect to Google, my computer, or client, will go to the Google server through the Internet and show me the information. By the way, is the time we access the web always constant? That's not the case at all. Therefore, the server computer must always be turned on because no one knows which client will access when.

The client should have a program called a web browser to access the web, while the server should have a program called a web server, which should always be turned on, as mentioned above. Therefore, our computers must have software called __daemon, service__.
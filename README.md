# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:

write C programs to illustrate IPC using pipes mechanisms

### ALGORITHM: IPC using pipes

1. Create a child process usingfork()

2. Create a simple pipe with C, we make use of the pipe() systemcall.

3. Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting

4. Close the read end of parent process using close() and perform writeoperation

5. Close the write end of child process and performreading

6. Display thetext.

## PROGRAM:
```
#include <stdio.h>

int main()

{

int fd[2],child; char a[10];

printf("\n Enter the string:");

scanf("%s",a);

pipe(fd);

child=fork();

if(!child)

{

close(fd[0]);

write(fd[1],a,5); wait(0);

}

else

{

close(fd[1]);

read(fd[0],a,5); printf("The string received from pipe is: %s",a);

}

return 0;

}
```

### OUTPUT:

<img width="292" alt="image" src="https://github.com/JayanthYadav123/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/94836154/07511686-d774-4ded-9e7c-16e64b6e2a3f">


## RESULT:
Thus, IPC using pipes mechanisms is illustrated using c program successfully

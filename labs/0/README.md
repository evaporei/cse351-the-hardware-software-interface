# Lab 0: C Warmup

https://courses.cs.washington.edu/courses/cse351/16sp/lab-0.html

## To compile and run

```
gcc -g -Wall -std=gnu99 -o arrays arrays.c
```

## Simple output

```
Filling an array at address 0x7ffcad58d250 with 10 values
Done!
Filling an array at address 0x7ffcad58d234 with 1 values
Done!
Filling an array at address 0x7ffcad58d240 with 4 values
Done!
Filling an array at address 0x560963cf9670 with 5 values
Done!
```

## Filling array with bigger length output

```
Filling an array at address 0x7ffe7bff3b40 with 15 values
Done!
Filling an array at address 0x7ffe7bff3b24 with 1 values
Done!
Filling an array at address 0x7ffe7bff3b30 with 4 values
Done!
Filling an array at address 0x560707c11670 with 5 values
Done!
*** stack smashing detected ***: <unknown> terminated
fish: “./arrays” terminated by signal SIGABRT (Abort)
```

## Valgrind simple output

```
==9422== Memcheck, a memory error detector
==9422== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==9422== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==9422== Command: ./arrays
==9422==
Filling an array at address 0x1fff0001e0 with 10 values
Done!
Filling an array at address 0x1fff0001c4 with 1 values
Done!
Filling an array at address 0x1fff0001d0 with 4 values
Done!
Filling an array at address 0x522d480 with 5 values
Done!
==9422==
==9422== HEAP SUMMARY:
==9422==     in use at exit: 0 bytes in 0 blocks
==9422==   total heap usage: 2 allocs, 2 frees, 1,044 bytes allocated
==9422==
==9422== All heap blocks were freed -- no leaks are possible
==9422==
==9422== For counts of detected and suppressed errors, rerun with: -v
==9422== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```

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

## Valgrind missing free output

```
==9525== Memcheck, a memory error detector
==9525== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==9525== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==9525== Command: ./arrays
==9525==
Filling an array at address 0x1fff0001e0 with 10 values
Done!
Filling an array at address 0x1fff0001c4 with 1 values
Done!
Filling an array at address 0x1fff0001d0 with 4 values
Done!
Filling an array at address 0x522d480 with 5 values
Done!
==9525==
==9525== HEAP SUMMARY:
==9525==     in use at exit: 20 bytes in 1 blocks
==9525==   total heap usage: 2 allocs, 1 frees, 1,044 bytes allocated
==9525==
==9525== LEAK SUMMARY:
==9525==    definitely lost: 20 bytes in 1 blocks
==9525==    indirectly lost: 0 bytes in 0 blocks
==9525==      possibly lost: 0 bytes in 0 blocks
==9525==    still reachable: 0 bytes in 0 blocks
==9525==         suppressed: 0 bytes in 0 blocks
==9525== Rerun with --leak-check=full to see details of leaked memory
==9525==
==9525== For counts of detected and suppressed errors, rerun with: -v
==9525== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```

## After TODO(4) output

```
Filling an array at address 0x7ffdecd5c600 with 10 values
Done!
Filling an array at address 0x7ffdecd5c5dc with 1 values
Done!
Filling an array at address 0x7ffdecd5c5f0 with 4 values
Done!
Filling an array at address 0x55d15b665670 with 5 values
Done!
Filling an array at address 0x55d15b665670 with 4 values
Done!
```

One interesting note, is that it seems like the same memory location was used both to allocate the `heap_array` and the `four_ints_ptr`, they were just used at different moments.

Also, `valgrind` went ok too:

```
==11563== Memcheck, a memory error detector
==11563== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==11563== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==11563== Command: ./arrays
==11563==
Filling an array at address 0x1fff0001e0 with 10 values
Done!
Filling an array at address 0x1fff0001bc with 1 values
Done!
Filling an array at address 0x1fff0001d0 with 4 values
Done!
Filling an array at address 0x522d480 with 5 values
Done!
Filling an array at address 0x522d4e0 with 4 values
Done!
==11563==
==11563== HEAP SUMMARY:
==11563==     in use at exit: 0 bytes in 0 blocks
==11563==   total heap usage: 3 allocs, 3 frees, 1,060 bytes allocated
==11563==
==11563== All heap blocks were freed -- no leaks are possible
==11563==
==11563== For counts of detected and suppressed errors, rerun with: -v
==11563== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
```

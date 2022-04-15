---
title: "打印C堆栈函数"
tags: 
 - "编程语言"
 - "C"
categories: 
 - "编程语言"
 - "C"
---

``` c
#include <stdio.h>
#include <execinfo.h>
#define STACK_SIZE 32
static void printStack(void)
{
    void *trace[STACK_SIZE];
    size_t size = backtrace(trace, STACK_SIZE);
    char **symbols = (char **)backtrace_symbols(trace,size);
    size_t i = 0;
    for(; i<size; i++)
    {
        printf("%d--->%s\n", i, symbols[i]);
    }
    return;
}
```

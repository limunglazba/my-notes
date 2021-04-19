# Asyncio


- [Definition](#definition)
- [asyncio.create_task()](#asynciocreate_task)

### Definition

- Asyncio is a library to write concurrent code (_asynchronous functions or coroutines_) using the **async/await syntax.** 
- Functions (coroutines) are defined as **async def** instead of **def**
- Concept: 
    (1) establish the main loop (event loop) 
    (2) add tasks to the loop and define how the loop runs them

```cmd
import asyncio
import time

async def say_after(delay, what):
    await asyncio.sleep(delay)
    print(what)

async def main():
    print(f"started at {time.strftime('%X')}")

    await say_after(1, 'hello')
    await say_after(2, 'world')

    print(f"finished at {time.strftime('%X')}")

asyncio.run(main())
```

### asyncio.create_task() 

function to run coroutines concurrently as asyncio  
```cmd
async def main():
    task1 = asyncio.create_task(
        say_after(1, 'hello'))

    task2 = asyncio.create_task(
        say_after(2, 'world'))

    print(f"started at {time.strftime('%X')}")

    # Wait until both tasks are completed (should take
    # around 2 seconds.)
    await task1
    await task2

    print(f"finished at {time.strftime('%X')}")
```

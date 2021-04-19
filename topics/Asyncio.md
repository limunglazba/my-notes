# Asyncio


- [Definition](#definition)
- [asyncio.create_task()](#asyncio.create_task())

### Definition

Asyncio is a library to write concurrent code (_asynchronous functions or coroutines_) using the **async/await syntax.**

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

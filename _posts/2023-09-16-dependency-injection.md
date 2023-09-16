---
layout: post
title: On Python Dependency Injection
category: algorithm, python
tags: [dependency injection, python, inversion of control, service locator, svcs]
---

One interesting dependency injestion (service locator) framework

[svcs](https://github.com/hynek/svcs/tree/main): from the author of attrs (where the idea of dataclass comes from)
- [svcs docs](https://svcs.hynek.me/en/latest/index.html)
- [svcs discussions](https://github.com/hynek/svcs/discussions)


[How to initialise a global object or variable and reuse it in every FastAPI endpoint?](https://stackoverflow.com/questions/76322463/how-to-initialise-a-global-object-or-variable-and-reuse-it-in-every-fastapi-endp/76322910#76322910)


```python
from fastapi import FastAPI, Request
from contextlib import asynccontextmanager


@asynccontextmanager
async def lifespan(app: FastAPI):
''' Run at startup
	Initialise the Client and add it to request.state
'''
n_client = NotificationClient()
yield {'n_client': n_client}
''' Run on shutdown
	Close the connection
	Clear variables and release the resources
'''
n_client.close()


app = FastAPI(lifespan=lifespan)


@app.get('/')
async def main(request: Request):
n_client = request.state.n_client
# ...
```

starlette lifespan: https://www.starlette.io/lifespan/#lifespan-state

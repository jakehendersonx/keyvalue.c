# keyvalue.c

A tiny key value store with asynchronous handling in pure C.

### Core Approach

- event loop architecture for I/O
- thread pool design for CPU work
- light coupling of server and request handling
- memory management between components
- simple error handling

### Key Design Points:

- event loop handles I/O multiplexing
- fixed thread pool processes CPU work
- zero-copy between event loop and workers
- lock-free I/O path
- predictable resource usage
- simple error handling

### Advantages

- can handle 10k+ connections
- clean separation of I/O and computation
- no thread creation overhead
- easy to reason about and debug
- minimal lock contention

### TCP server

- event driven I/O using epoll
- non-blocking socket operations
- event handler callback pattern

### Container

This code was developed in a linux docker container on an
arm64 macbook pro.

```bash
docker build -t keyvalue
docker run -v $(pwd):/code --name keyvalue.c -it keyvalue
```

### compiling

```bash
make # build
make run # build and run
make clean # remove build files
```

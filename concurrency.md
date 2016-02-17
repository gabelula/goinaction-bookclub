When possible always choose the option of write programs as one linear path of code as it is s simple to write and mantain.

Examples when concurrency is a good option

- web service that can receive multiple requests for data on individual sockets at the same time

## Concurrency in GO

It is the ability for functions to run independent of each other.

go runtime scheduler : manages all the goroutines that are created and need processor time

### "[Communicating sequential processes](https://en.wikipedia.org/wiki/Communicating_sequential_processes)"

It describe patterns of interactions in concurrent systems.  Message-passing model that works by communicating data instead of locking data to synchronize access. The key data type for synchronizing and passing messages is called a channel.

## Concurrency versus Parallelism

### A process

It is like a container that holds all the resources an application uses and maintains as it runs.

### A thread

It is a path of execution that is scheduled by the operating system to run the code that you write in your functions.


### How the scheduler works.

![Ardan Labs](https://github.com/ardanlabs/gotraining/raw/master/topics/goroutines/scheduler.png)

### Difference between concurrency and parallelism.

![Ardan Labs](https://github.com/ardanlabs/gotraining/raw/master/topics/goroutines/parallel.png)

## Goroutines

[Listing 6.1](https://play.golang.org/p/LC1VgZZzO9)

[Listing 6.4](https://play.golang.org/p/WU1p9-_RMN)

## Race conditions

When two or more goroutines have unsynchronized access to a shared resource and attempt to read and write to that resource at the same time.

[Listing 6.10](https://play.golang.org/p/_BpVuJ2jga)

![Ardan Labs](https://github.com/ardanlabs/gotraining/raw/master/topics/data_race/data_race.png)

### Tool to detect race conditions in your code

```
go build -race
./example
```

## Locking shared Resources

### Atomic package

Low-level locking mechanisms for synchronizing access to integers and pointers

### Sync package

A [mutex](https://github.com/ardanlabs/gotraining/blob/master/topics/data_race/example4/example4.go) is used to create a critical section around code that ensures only one goroutine at a time can execute that code section.

## Channels

[Channels](https://github.com/ardanlabs/gotraining/blob/master/topics/channels/README.md) synchronize goroutines as they send and receive the resources they need to share between each other.

### Unbuffered channels

![Ardan Labs](https://github.com/ardanlabs/gotraining/raw/master/topics/channels/unbuffered.png)

### Buffered channels

![Ardan Labs](https://github.com/ardanlabs/gotraining/raw/master/topics/channels/buffered.png)

[Listing 6.20](https://play.golang.org/p/kuxUFMqy-9)

## Resources

. [Hardcore Go - Concurrency](https://github.com/ardanlabs/gotraining/tree/master/courses/hardcorego/concurrency)

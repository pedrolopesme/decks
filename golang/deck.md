---
id: a8f9c2d1-4b1a-4c92-8f3e-1d5e6a9f8b22
name: Golang Concurrency Interview Prep
description: 20 high-level concurrency questions frequently asked in Big Tech interviews.
author: Gemini
tags:
  - golang
  - concurrency
  - backend
---

## 1. What is the difference between concurrency and parallelism?
Concurrency is dealing with lots of things at once (composition of tasks); Parallelism is doing lots of things at once (execution of tasks).

## 2. How does the Go scheduler (G-M-P model) work?
G (Goroutine), M (Machine/Thread), and P (Processor/Context) work together to multiplex many goroutines onto fewer OS threads.

## 3. What happens if you send to a nil channel?
Sending to a nil channel blocks the goroutine forever, causing a deadlock if no other path exists.

## 4. What is the purpose of the `select` statement?
`select` lets a goroutine wait on multiple communication operations, choosing the first one that is ready.

## 5. Can you have a race condition in a thread-safe language like Go?
Yes. Using shared memory without proper synchronization (mutexes, channels) leads to race conditions even with Go's memory model.

## 6. What is the difference between `sync.Mutex` and `sync.RWMutex`?
`RWMutex` allows multiple readers or a single writer, whereas `Mutex` allows only one goroutine access regardless of the operation.

## 7. What is a "buffered channel" and when should you use it?
A buffered channel holds a specific number of elements; it is used to decouple sender/receiver speed and prevent blocking.

## 8. How do you detect race conditions in Go?
Use the built-in race detector by running your code with the `-race` flag: `go run -race main.go`.

## 9. How do you gracefully stop a goroutine?
Pass a `context.Context` to the goroutine and listen to its `Done()` channel to trigger a shutdown.

## 10. Why is `sync.WaitGroup` used?
It is used to wait for a collection of goroutines to finish their execution before proceeding.

## 11. What is the danger of `time.Sleep` in production code?
It is imprecise and inefficient; using `context` or channels for synchronization is preferred for responsiveness.

## 12. How does Go’s memory model handle synchronization?
It defines the "happens-before" relationship to guarantee memory visibility between goroutines.

## 13. What is the `fan-out` and `fan-in` pattern?
Fan-out distributes work across multiple goroutines; fan-in multiplexes their results back into a single channel.

## 14. What are the common pitfalls when using channels?
Deadlocks, leaking goroutines, sending to/closing nil/closed channels.

## 15. How do you implement a singleton pattern in Go?
Use `sync.Once` to ensure a piece of code (like initialization) runs exactly once.

## 16. What is an atomic operation and why use `sync/atomic`?
Atomic operations are CPU-level instructions that complete without interruption; they are faster than mutexes for simple counter increments.

## 17. What is a "goroutine leak"?
A goroutine that starts but never finishes or sends data back, remaining in memory indefinitely.

## 18. How does `sync.Map` differ from a standard `map` with a `Mutex`?
`sync.Map` is optimized for concurrent scenarios where keys are often stable (read-heavy or write-once-read-many).

## 19. What is the purpose of `runtime.Gosched()`?
It yields the processor, allowing other goroutines to run.

## 20. When should you prefer channels over mutexes?
Use channels when passing ownership of data or coordinating sequences; use mutexes for protecting internal state/caching.

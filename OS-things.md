# Classical Problem Of Synchronization
---

* Classical problems synchronization:
	* Producer & Consumer(Bounded-Buffer) Problem
	* Readers and Writers Problem
	* Dining-Philosophers Problem
	* Sleeping Barber Problem

## Producer-Consumer problem

Two types of processes are there:
* Producer process - produce the information
* Consumer process - consume the information produced by producer

* Producer process produces information that is consumed by a Consumer process.
* The information is passed from the Producer to the Consumer via a **buffer**.

Two types of buffers can be used:
* `unbounded-buffer` places no practical limit on the size of the buffer
* `bounded-buffer` assumes that a fixed buffer size

Three things to take care of:
* When the `buffer` is full, no producer process will produce anything.
* When the `buffer` is empty, no consumer process will consume the data.
* No producer or consumer problem should work simultaneous on bounded buffer because buffer size is limited so we have to establish a synchronization between producer and consumer.

We can implement producer-consumer buffer with the `linear` or `circular` queue, with the position of `front` as _producer_ and `rear` as _consumer_.

Two ways to solve:

* **Simple Queue(Shared data):**

```c
# define BUFFER SIZE 8

int buffer [BUFFER SIZE];

int in = 0;  // in points to next free positon
int out = 0;  // out points to first full postion
int Counter = 0;
```
	Counter is incremented every time we(producer) add a new item(data) to the buffer & decremented every time we(consumer) remove one item from the buffer.

**produecer problem**
```c
while (True) {
	/* produece an item is nextProdueced*/
	while (counter == BUFFER_SIZE);
	/* do nothing */
	buffer[in] = nextProduced;
	in = (in + 1) % BUFFER_SIZE;
	counter ++;
}
```

**Consumer problem**
```c
while (True) {
	while (counter == 0); /* do nothing */
	nextConsumed = buffer[out];
	out = (out + 1) % BUFFER_SIZE;
	counter --;
	/* consume the item in nextConsumed */
}
```

### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?
The DevBoard checks if the serial port's receive buffer is not empty and when triggered it validates the data received. It is different because there is two-way communication between computer and DevBoard which makes it possible to check for invalid states.

### What does `detached_callback` do? What would happen if it wasn't used?
It allows code to be spawned into a thread, making the function run simultaneous with other functions. Not using this would cause freezing when a section takes too much time to run

### What does `LockedSerial` do? Why is it _necessary_?
It prevents multiple threads to access the serial port at once. If not in place, it could lead to undefined behavior.
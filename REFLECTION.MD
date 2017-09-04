# CarND-PID-Control-Project
## Student reflections on tuning PID.
## Thomas Brightwell, September 2017

I do have some real world experience with PIDs. The one I tend to remember is when we used to test McLaren F1 engines. The engines had to be tested at very particular atmospheric conditions (temperature, pressure, humidity), so we used PID controllers to regulate the air going into each test cell. We were able to gather live data, and watch the effect of the tuning on the system live.

In terms of tuning the PID for the car, I started with the PID Controller Q&A video here
https://www.youtube.com/watch?v=YamBuzDjrs8

but using my own notes on using Docker rather than Ubuntu
https://discussions.udacity.com/t/getting-started-with-docker-and-windows-for-the-ekf-project-a-guide/320236

I was able to code along pretty much in real time with the instructor video, getting to a point where I had a PID driving a car (shakily) around the track. The Docker approach was pretty fast to compile and reinitialise with new coefficient guesses, so I felt no need to extend the project towards using Twiddle, or even simply taking in constructor arguments for P, I and D coefficients.
From there I drew upon my own knowledge of PIDs to continue refining the coefficients.
I focused first upon Kp and Kd, tuning them on a roughly logarithmic basis. Kp directly affects the magnitude of turning. Bigger value = bigger turns. But leads to wobble. Kd reduces oscillations. Between the two I looked for a sweet spot where the car turned sufficiently, without oscillating wildly.
By the end of the video I was at Kp 0.1, Ki 0, Kd 5, which was pretty close to my final chosen values of Kp 0.1, Ki 0.0001, Kd 4. 
Integral errors are additive over time, so I wanted a very small value here.

Once happy with the values, I recorded a video of a lap of the simulator,
[Output Video](https://github.com/brightwellt/CarND-PID-Control-Project/output_video.mp4)
which can be found in the github repository.


# Real-time wireless video streaming and object-detection
<b>Abstract</b>: The authors have built a real-time object detection system with wireless video streaming capabilities for remote monitoring purposes. The primary component of this system is a video camera equipped NVIDIA JETSON TK1 platform, that executes concurrent tasks for image acquisition, wireless video streaming and object detection. For viewing the live video stream and the object-detection results, a remote terminal in the form of a laptop computer is used. Transmission of video frames was accomplished by using UDP packets sent over a WiFi channel, and the object-detection was implemented with the help of Amazon Rekognition -- a deep learning platform for image detection and recognition. The primary goal of this project was to implement an efficient software architecture that is able to accomplish the above time-critical tasks in a soft real-time fashion.
<br>
<img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/Block_diagram.png" alt="Block Diagram">

 <p> <b> Capabilities Requirements: </b> </p>

In this section, details have been presented regarding the features, resources, and constraints required for our real-time wireless video streaming and object-detection system to operate. Based on our preliminary tests, and proof-of-concept analysis, the following are the requirements for our system to accomplish its desired functionality:<br>
●	Camera with good optical resolution and platform which can process high frame rate for clear video rendering (at least 10 fps)<br>
●	Network infrastructure with requisite bandwidth for handling transfer of 160x120 frames (10-bit encoding) at the desired frame rate.<br>
●	Computing platform with image acquisition, processing, and display capabilities (camera driver, OpenCV) and Python support for scripting<br>
●	Machine/Deep learning based platform for object detection and recognition<br>
●	Internet connectivity for communicating with remote object detection platform<br>
●	Remote computing platform (laptop) with GUI and software framework (OpenCV, GCC, Python) for running server code<br>
●	Text-to-speech engine <br>

<p> <b> Feasibility and Safety Analysis of Service Set:  </b> </p>

The schedule for the above four services was simulated in Cheddar using prio(Sequencer)>prio(S1)>prio(S3)>prio(S2). The following screenshot in Fig. 1 shows a simulation of the proposed real-time services using the RM priority preemptive scheduling policy. We found that all the services were observed to meet their deadlines, and the CPU utilization was 0.95. This is in agreement with our estimated margin of 6%.

 <img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/Feasibility_tests.png" alt="Feasibility test">
 
 <p> <b> Results and Performance: </b> </p>

Presented below, are results of a few sample test cases that were employed to verify the execution of the three services. The ‘TX’ labels correspond to the Jetson board which acts as the transmitter for the image stream. The ‘RX’ labels correspond to the laptop computer which acts as the receiver for the image stream and object-detection results.
<br>
<b> TX1 </b>
<img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/tx1.png" alt="TX1">
<br>
<b> RX1 </b>
<img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/rx1.png" alt="RX1">
<br>
<b> TX2 </b>
<img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/tx2.png" alt="TX2">
<br>
<b> RX2 </b>
<img src="https://github.com/sral1993/ECEN-5623-Real-Time-Embedded-Systems/blob/master/Client/rx2.png" alt="RX2">


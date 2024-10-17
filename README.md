<h1>Manual</h1>
<p>In this manual we will be making a HUB. This HUB will turn on a light when it's dark out, but only when a person is present in the room</p>
<p>Technical requirements:</p>
<ul>
  <li>A NodeMCU (with WIFI chip)</li>
  <li>A cable from mico-usb to usb-a</li>
  <li>An LED-strip</li>
  <li>An infrared sensor (PIR Motion Sensor)</li>
  <li>A connector with 4 wires</li>
</ul>

![Frame 1](https://github.com/user-attachments/assets/ca937173-8e01-4891-af04-8f267f77c3d3)

<p>You will also need to download a program called Arduino IDE. Follow this link to download the program: https://www.arduino.cc/en/software</p>

![Frame 2](https://github.com/user-attachments/assets/408ccd70-5f77-4748-8d7d-8ece24d88e43)

<p>Click on Windows Win 10 and newer, 64 bits highlighted in red. Download the program and run it.</p>

<p>Open a New Sketch (CTRL + N) if you don’t already have one open like below.</p>

![image](https://github.com/user-attachments/assets/5d2c1cf8-3266-4cdf-b419-dbbd9c515e04)


<p>Now we can finally start coding. </p>

<h2>Chapter 1. Connecting your NodeMCU</h2>

<p>Step 1. Open a New Sketch</p>

<p>Step 2. Plug in the Micro-USB into your NoteMCU and plug the USB-A in your computer.</p>

![Frame 3](https://github.com/user-attachments/assets/f3fa753f-b91f-4c49-9019-99dfb1ce74ec)

<p>Step 3. Select the right board. Go to Tools > Board:”...” > esp8266 > NodeMCU 1.0 (ESP-12E Module)</p>

![Frame 4](https://github.com/user-attachments/assets/3790abe6-427e-4b20-9c27-90a1d8390d22)

<p>Step 4. Select the right port. This is where you plugged in the USB-A. Go to Tools > Port: “...” > COM 7. Go to Step 5 if you don’t know which port you need to select. Go to Step 7 if you did this step successfully.</p>

![Frame 5](https://github.com/user-attachments/assets/dd14f4eb-3377-4ac5-afc1-7e3d7f24549c)

<p>Step 5. Press this button on the top left. (The text in the button might look different for you) and click “Select other board and port…”</p>

![Frame 6](https://github.com/user-attachments/assets/bac98bfe-e76a-4a9f-b482-b8930d5b0580)

<p>Step 6. Type “nodemcu 1.0” in the blue highlighted box and select the right board “NodeMCU 1.0 (ESP-12E Module)” and select the COM on the right with the text “(USB)” on the right. This is the connected USB. Press ok.</p>

![Frame 7](https://github.com/user-attachments/assets/6246f485-50bd-46be-9f77-f4d32b3ec249)

<p>Step 7. To check if your NodeMCU is connected correctly, press the upload button on the top left. When the upload is done you will see the message “Done uploading” on the bottom left.</p>

![Frame 8](https://github.com/user-attachments/assets/607cfe88-dfb2-44b5-a939-ea79d34dd926)

<p>If your upload was unsuccessful you will see the following error message in the Output.</p>

![Frame 9](https://github.com/user-attachments/assets/edf984c5-46fe-4bf3-bc79-a92e4f9582e1)

<p>Go back to Step 6 and select a different port until the error message no longer shows after you upload the code.</p>

<h2>Chapter 2. Checking the connection of your NodeMCU</h2>

<p>Step 1. Copy the following code and paste it in the void Setup.</p>

  <p>Serial.begin(9600);</p>
  <p>Serial.println("Hello world");</p>

<p>Like this:</p>

![image](https://github.com/user-attachments/assets/15ad2f9c-e36a-4e58-91b9-c657e54123ba)

<p>Step 2. Upload the code by pressing the arrow in the top right (like Step 7 from Chapter 1). And open the Serial Monitor (highlighted red in the top right) when it is done uploading. Look at the output it gives (in the yellow highlighted box)</p>

![Frame 10](https://github.com/user-attachments/assets/194f90ed-9d8c-4206-83ed-72aa3ac256d4)

<p>If you see “Hello world” in the Serial Monitor, you have successfully connected your NodeMCU.</p>

<h2>Chapter 3. Weather API</h2>

<p>In this chapter we will connect the ModeMCU to a weather API. The weather API will give us a real time forecast.</p>

<p>Step 1. Make an account for <a href="https://openweathermap.org">Open Weather Map</a> Use the sign in button on the top right, highlighted red below.</p>


![Frame 12](https://github.com/user-attachments/assets/a0f30b3c-8c8d-4809-a284-6abe34539d0b)

<p>Make a new account by using the button highlighted red below.</p>

![Frame 11](https://github.com/user-attachments/assets/aace5bcc-1b9c-48f5-9a18-2cabdcebb81c)

<p>Fill in your information in the form and create your account.</p>

<p>Step 2. Copy the code from <a href="https://gist.github.com/icecream4all/7e9db0333f44192a6071eb73efe23329#file-nodemcu-weather-ino">This website</a> and paste it in a New Sketch (CTRL + N)</p>




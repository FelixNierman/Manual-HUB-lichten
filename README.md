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

  <code>Serial.begin(9600);</code>
  <br>
  <code>Serial.println("Hello world");</code>

<p>Like this:</p>

![image](https://github.com/user-attachments/assets/15ad2f9c-e36a-4e58-91b9-c657e54123ba)

<p>Step 2. First, upload the code by pressing the arrow in the top left (like Step 7 from Chapter 1). Secondly, open the Serial Monitor (highlighted red in the top right) when it is done uploading. Look at the output it gives (in the yellow highlighted box)</p>

![Frame 10](https://github.com/user-attachments/assets/194f90ed-9d8c-4206-83ed-72aa3ac256d4)

<p>If you see “Hello world” in the Serial Monitor, you have successfully connected your NodeMCU.</p>

<h2>Chapter 3. Connecting the Weather API</h2>

<p>In this chapter we will connect the ModeMCU to a weather API. The weather API will give us a real time forecast.</p>

<p>Step 1. Make an account for <a href="https://openweathermap.org">Open Weather Map</a> Use the sign in button on the top right, highlighted red below.</p>


![Frame 12](https://github.com/user-attachments/assets/a0f30b3c-8c8d-4809-a284-6abe34539d0b)

<p>Make a new account by using the button highlighted red below.</p>

![Frame 11](https://github.com/user-attachments/assets/aace5bcc-1b9c-48f5-9a18-2cabdcebb81c)

<p>Fill in your information in the form and create your account.</p>

<p>Step 2. Copy the code from <a href="https://gist.github.com/icecream4all/7e9db0333f44192a6071eb73efe23329#file-nodemcu-weather-ino">This website</a> and paste it in a New Sketch (CTRL + N)</p>

<p>Step 3. Start a hotspot on you phone</p>

<p>Step 4. Paste the name of your hotspot and the password in the code. Replace <code>"YOUR PHONE HOTSPOT HERE"</code> with the name of your hotspot and replace <code>"YOUT HOTSPOT PASSWORD"</code> with the password of your hotspot</p>

![image](https://github.com/user-attachments/assets/ac6c7cb7-6318-4a16-b70a-aa921d204372)

<p>Step 5. Replace <code>"Amsterdam,NL"</code> with the name of your city.</p>

![image](https://github.com/user-attachments/assets/64d19f71-fc5c-43f5-9c2c-6c8e433a702a)

<p>Step 6. Go back to the open weather map website, click on your account and go to "Your API keys".</p>

![Frame 13](https://github.com/user-attachments/assets/5a6ae82d-0db4-4b23-8144-6d8fac61a3f5)

<p>Step 7. Copy your API key.</p>

![Frame 14](https://github.com/user-attachments/assets/4a1b1f80-f1e9-4309-8437-18e00ff43d05)

<p>Step 8. Replace <code>"YOUR API KEY"</code> with your API key.</p>

![image](https://github.com/user-attachments/assets/6c7d2051-e078-4690-8b85-bf924a986440)

<p>Step 9. Upload the code to your NodeMCU.</p>

<p>Step 10. Open the Serial Monitor to check if the weather API was successfully connected. You should see the following in your Serial Monitor.</p>

![image](https://github.com/user-attachments/assets/7e447227-a69e-4407-ad54-d8a48728024c)

<p>If you see the following error message, disconnect your NodeMCU from the micro-usb cable and plug it back in. It should reconnect.</p>

![image](https://github.com/user-attachments/assets/b72b7122-26c6-47a2-a978-11acaf236295)

<p>You now have the weather API successfully connected.</p>

<h2>Chapter 4. Editting the Code</h2>

<p>Step 1. Change <code>"forecast"</code> in the following code to <code>"weather"</code>.</p>

![Frame 15](https://github.com/user-attachments/assets/71a0ca37-c464-4635-a18e-b2e19e6b3da7)

![Frame 16](https://github.com/user-attachments/assets/7c2fd10c-d6b8-46e6-a646-54436840a70f)

<p>Step 2. Install the library NTPClient by Fabrice Weinberg.</p>

![image](https://github.com/user-attachments/assets/bda00420-9498-43b7-9d3c-26f06c0ae359)

<p>Step 3. Paste the following code in the top of your file to include the newly installed library.</p>

<code>#include <NTPClient.h><br>
#include <WiFiUdp.h></code>

<p>Like this:</p>

![image](https://github.com/user-attachments/assets/11f5bdc9-e9a2-44e7-8134-ef19410b8d1c)

<p>Step 4. Paste the following code a little bit below the other code you just added like in the picture below.</p>

<code>WiFiUDP ntpUDP;<br>
NTPClient timeClient(ntpUDP, "pool.ntp.org", 3600, 60000); // Sync with NTP server every minute<br>
<br>
int lightPin = 5;  // GPIO pin connected to the light<br>
unsigned long sunsetTime = 0; // To store the sunset time in Unix timestamp format</code>

![Frame 20](https://github.com/user-attachments/assets/28fea7bd-236b-424f-80c0-ce6689c03509)

<p>Step 5. Paste the following code in the <code>void setup</code> as shown below.</p>

<p><code>  timeClient.begin();  // Start NTP client</code></p>

![image](https://github.com/user-attachments/assets/3107e77f-6078-4260-bd85-b8fa9ab72b1e)

<p>Step 6. Paste the following code in the <code>void loop</code> as shown below.</p>

<p><code>timeClient.update();  // Update current time from NTP server<br>
<br>
unsigned long currentTime = timeClient.getEpochTime();<br>
if (currentTime > sunsetTime && sunsetTime != 0) {<br>
  // It's after sunset, turn on the light<br>
  digitalWrite(lightPin, HIGH);<br>
  Serial.println("Turning on the light, it's after sunset.");<br>
} else {<br>
  // It's before sunset or data not available yet<br>
  digitalWrite(lightPin, LOW);<br>
  Serial.println("Light is off.");<br>
}<br>
<br>
delay(60000);  // Check once every minute</code></p>

![image](https://github.com/user-attachments/assets/5301bd72-f17b-4c36-8027-d2a43df2f7d5)

<p>Step 7. Paste the follow code in the <code>void parseJson</code> as shown below.</p>

<p><code>  // Get sunrise and sunset<br>
unsigned long sunrise = doc["sys"]["sunrise"];<br>
unsigned long sunset = doc["sys"]["sunset"];<br>
<br>
// Convert Unix timestamp to human-readable format<br>
time_t rawtime = sunrise;<br>
struct tm * timeinfo = localtime(&rawtime);<br>
Serial.print("Sunrise: ");<br>
Serial.println(asctime(timeinfo));<br>
<br>
rawtime = sunset;<br>
timeinfo = localtime(&rawtime);<br>
Serial.print("Sunset: ");<br>
Serial.println(asctime(timeinfo));<br>
<br>
sunsetTime = doc["sys"]["sunset"];<br>
Serial.print("Sunset time (Unix): ");<br>
Serial.println(sunsetTime);</code></p>

![Frame 23](https://github.com/user-attachments/assets/054e0cc0-6ab0-4d17-b7f2-c3578fe16a4a)

<h2>Chapter 5. Connecting the LED-strip</h2>

<p>Step 1. Install the library "Adafruit NeoPixel" by Adafruit.</p>

![image](https://github.com/user-attachments/assets/4c328844-34ac-4107-91bc-36ebbb95772c)










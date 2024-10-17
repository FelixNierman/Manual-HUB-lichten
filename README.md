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

<p>Step 1. Change <code>"forecast"</code> in the <code>void makehttpsRequest</code> to <code>"weather"</code>.</p>

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

<p>Step 6. Paste the following code in the <code>void loop</code>. This will compare the current time with the time of sunset and give feedback by turning on a light (we dont yet have connected) and by giving us a Serial.print.</p>

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

<p>Like this:</p>

![image](https://github.com/user-attachments/assets/5301bd72-f17b-4c36-8027-d2a43df2f7d5)

<p>Step 7. Paste the follow code in the <code>void parseJson</code>. This code takes the data from the weather API and turns it into something we can read and use in our code.</p>

<p><code>// Get sunrise and sunset<br>
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

<p>If you look in the Serial Monitor, you can see the time the sun will set and come up again.</p>

![image](https://github.com/user-attachments/assets/ff2faf62-72cf-4895-9c4e-e8f9e8500494)

<h2>Chapter 5. Connecting the LED-strip</h2>

<p>Step 1. Install the library "Adafruit NeoPixel" by Adafruit.</p>

![image](https://github.com/user-attachments/assets/4c328844-34ac-4107-91bc-36ebbb95772c)

<p>Step 2. Paste the following code below the other libraries you have included as shown below.</p>

<p><code>#include <Adafruit_NeoPixel.h><br>
#define PIN D1<br>
#define NUMPIXELS 15<br>
Adafruit_NeoPixel pixels(NUMPIXELS, PIN, NEO_GRB + NEO_KHZ800);</code></p>

![image](https://github.com/user-attachments/assets/d8b062bb-30f2-4268-a40f-54c040134c9d)

<p>Step 3. Connect your LED-strip to your NodeMCU.</p>

<ul>
  <li>The black wire connects to GND on the NodeMCU</li>
  <li>The red wire connects to 3v3 on the NodeMCU</li>
  <li>The yellow wire connects to D1 on your NodeMCU</li>
</ul>

![Frame 25](https://github.com/user-attachments/assets/e66610d3-0c8c-4cc4-a6ed-b14fdd3b9003)

<p>Step 4. Paste the following code in the <code>void setup</code> as shown below. This will enables the LED-strip, but doesnt turn on the lights.</p>

<p><code>pixels.begin();<br>
  pixels.show();</code></p>

![image](https://github.com/user-attachments/assets/2af58f8f-d62c-420c-a6df-c843b0b67966)

<p>Step 5. Remove <code>digitalWrite(lightPin, HIGH);</code> and paste the following code in your <code>void loop</code> in the else statement. Upload the code to check if your LED-strip works, as shown below.</p>

<p><code>pixels.setPixelColor(0, pixels.Color(255, 0, 0));<br>
pixels.show();</code></p>

![image](https://github.com/user-attachments/assets/79dc9614-9057-449d-a53f-89f358778565)

<p>If the sun is up, your light should turn red like the picture below.</p>

![image](https://github.com/user-attachments/assets/8c0b9778-87e0-4e96-b717-9e3eb07018a5)

<p>If it doesn't light up it might be because the sun has already set (paste the code in the if statement instead)</p>

<p>Step 6. Change the rgb value to (0, 0, 0) in the else statement to turn off the LED-strip and paste the code from the previous step in the if statement, but change the rgb value to (255, 255, 255) to turn on the LED-strip.</p>

<p><code>pixels.setPixelColor(0, pixels.Color(255, 255, 255));<br>
pixels.show();  </code></p>

![image](https://github.com/user-attachments/assets/858430ae-80ba-462e-933c-f5a0bd267e79)

<p>Step 7. Test if everything works. If you are following along during the day, there is a way to check if it also works at night. To do this you need to change <code>nameOfCity</code> to a city on the other side of the world.</p>

<p>Because it is daytime in Amsterdam at the moment of writing this, I used Tokyo Japan to check if it works. You can use any city by typing the name in English and using the Country code. This is a two letter code you can find on <a href="https://www.iso.org/obp/ui/#search">this website</a>.</p>

![image](https://github.com/user-attachments/assets/9d702e0b-974c-43a9-93f7-523672484ea7)

<h2>Chapter 6. Connecting the infrared sensor</h2>

<p>Step 1. Connect the PIR Motion sensor to your NodeMCU.</p>

<ul>
  <li>Black wire to GND</li>
  <li>Red wire to 3v3</li>
  <li>White wire keep unplugged</li>
  <li>Yellow wire D2</li>
</ul>

<p>Step 2. Check if the motion sensor works. Make a new sketch and paste the following code:</p>

<p><code>#define PIR_MOTION_SENSOR D2<br>
<br>
void setup() {<br>
  Serial.begin(9600);<br>
  pinMode(PIR_MOTION_SENSOR, INPUT);<br>
}<br>
<br>
void loop() {<br>
  int motion = digitalRead(PIR_MOTION_SENSOR);<br>
  Serial.print("PIR Sensor State: ");<br>
  Serial.println(motion);<br>
<br>
  if (motion == HIGH) {<br>
    Serial.println("Motion detected!");<br>
  } else {<br>
    Serial.println("No motion.");<br>
  }<br>
  <br>
  delay(1000);<br>
}</code></p>

<p>Step 3. Upload the code and take a look at the Serial Monitor.</p>

<p>If the Serial Monitor keeps giving you a "Motion detected!" it might be because of the following reasons.</p>

<ul>
  <li>Check if all your wires are connected correctly!</li>
  <li>Check if you call upon the second pin correctly: #define PIR_MOTION_SENSOR D2. If you use 2, instead of D2, it might not work.</li>
</ul>

<p>If the Serial Monitor also gives "No motion" you have successfully connected the motion sensor.</p>

<h2>Chapter 7. Integrating the motion sensor into your code</h2>

<p>Now that we know the motion sensor works, we need to use it in our code.</p>

<p>Step 1. Add the following code as shown below. This will allow the NodeMCU to recognise the motion sensor and also lower the sensitivity (this is to ensure it isn't always on high alert).</p>

<p><code>#define PIR_MOTION_SENSOR D2<br>
int pirState = LOW;  // Start with no motion detected<br>
long lastDetectionTime = 0;<br>
const long debounceDelay = 2000;  // 2-second delay for debouncing</code></p>

![image](https://github.com/user-attachments/assets/89f14e40-d5eb-4694-8137-d807af5eba8e)

<p>Step 2. Add the following code to your void setup like shown below.</p>

<p><code>pinMode(PIR_MOTION_SENSOR, INPUT);</code></p>

![image](https://github.com/user-attachments/assets/5f3dcbbd-d20b-4131-bee8-039aa7f9cc7a)

<p>Step 3. Take the code relating to the sunset and lights out of the loop and put them in a void of their own. Give this new void the name DayNight.</p>

<p>Before:</p>

![image](https://github.com/user-attachments/assets/ca5a6ffe-ef8f-4d7a-9e53-a915948d9966)

<p>After:</p>

![image](https://github.com/user-attachments/assets/926d27b5-d9d9-45e7-9a3f-563183358c1a)

<p>Step 4. Create a new void for detecting motion. When motion is detected, call on the DayNight function like below.</p>

![image](https://github.com/user-attachments/assets/59f9dcd4-0a3a-47ad-8379-d80e430b46d1)

<p>Now you have successfully made a HUB that detects if its dark out, turns on the lights accordingly, but only when movement is detected.</p>

<h2>Tips</h2>

<p>If you are checking if a line of code works by using the Serial Monitor, but it updates too fast. Try the <code>delay(60000); This will give it a delay of one second, you can lower or higher this.</code></p>

<p>If you are unsure if one of your peripherals works or not, make a New Sketch and test it there. This will save you a lot of cleaning up your code and give you a better insight of where the problem might lie.</p>

<p>If you ask ChatGPT to help you with coding, give him all your code, explain what you want and ask him to apply it in your code. The last part is very important if you are unsure of how the code works, otherwise you have to add it to your code yourself</p>

<p>Always, always, always save your code. It's a real bummer to code for an hour and lose everything because you didnt hit save.</p>

<h2>Common mistakes made</h2>

<p>When you are struggling with a new sensor like the Motion Sensor, look the product up. The website <a href="https://wiki.seeedstudio.com/Grove-PIR_Motion_Sensor/">Seeedstudio</a>shows you basic code to test the sensor and more information.</p>

<p>If something hasnt been working, dont always assume its your code. It is very easy to plug in a sensor wrong, like I did.</p>

<p>If you want to check if your lights turn when the sun is down by changing location, keep in mind that the current time doesnt change. This might cause you to think your code doesnt work, it does.</p>

# Womens_Safety_device

1. Overview

The system is a wearable safety device aimed at helping women during emergencies. It features GPS for location tracking and GSM for sending SMS alerts. The device is controlled by a microcontroller, like Arduino Nano or ESP32.

When the user presses the panic button, the system:

- Captures her real-time location using GPS.
- Sends an SOS message with her coordinates to registered contacts via GSM.
- Optionally updates the mobile app and cloud server for live tracking.

2. System Components
Component	Function
Microcontroller (Arduino Nano / ESP32)	Serves as the brain of the system, controlling GPS, GSM, and button input.
GPS Module (NEO-6M)	Tracks live latitude and longitude coordinates.
GSM Module (SIM800L)	Sends SMS messages with SOS and GPS location.
Panic Button	Triggers the emergency alert when pressed.
Battery (Li-ion)	Powers the entire circuit.
Mobile App (Flutter / Android Studio)	Shows live location and allows management of contacts.
Cloud Server (Firebase / AWS)	Stores location data and manages alerts via API.

3. Working Process (Step-by-Step)
Step 1 – Initialization

When powered on, the microcontroller initializes both GPS and GSM modules. It confirms that they are connected and ready to send or receive data.

Step 2 – Monitoring State

The system continuously listens for:

- Panic button presses.
- Updated GPS coordinates for real-time location updates.

Step 3 – Emergency Activation

When the panic button is pressed:

- GPS captures the current location (latitude and longitude).
- The MCU creates an SOS message such as: "HELP! I am in danger. My location: Latitude 12.957, Longitude 77.601. Please help!" 

The message is sent to predefined contacts, like family or police, via the GSM module as an SMS.

Step 4 – Cloud & App Communication

At the same time, location data is sent to the mobile app and cloud server:

- The app shows a live location map using the Google Maps API.
- The cloud stores each alert with a timestamp and GPS data for tracking and evidence.

Step 5 – Alert Notification

Emergency contacts receive the SOS message immediately. The mobile app or web dashboard can also notify authorities through push notifications or emails.

4. Software Workflow Summary

Power ON → Initialize modules. 

Wait for input (button press). 

If pressed → Capture GPS → Compose SOS → Send via GSM. 

Update cloud and mobile app. 

Continue monitoring (loop). 

5. Performance Evaluation

The system was tested under various conditions:

Parameter	Testing Condition	Observation
GPS Accuracy	Open sky and urban areas	Good accuracy in open spaces; minor delay in dense areas. 
Alert Time	Button press to SMS received	Few seconds, depending on the network. 
Battery Life	Continuous operation	Several hours of standby. 
Reliability	Tested for false triggers	Stable operation with low false positives. 

6. Key Advantages

Works even without internet in SMS mode. 

Compact and wearable design. 

Fast emergency response with direct location alerts. 

Cloud backup ensures data security and accessibility. 

7. Future Enhancements

The paper suggests improvements like:

- AI-based automatic distress detection using heart rate and motion sensors.
- 5G and IoT integration for quicker responses.
- Biometric sensors for health and panic detection.
- Blockchain storage for tamper-proof evidence.
- Integration with police networks for instant alerts.

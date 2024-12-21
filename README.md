ESP32-CAM Photo Capture and Upload to Firebase Storage
This project demonstrates how to capture photos with an ESP32-CAM module and upload them to Firebase Storage using the Firebase ESP32 SDK. The captured images are first saved in the internal LittleFS filesystem, then uploaded to Firebase Cloud Storage for remote access and storage. This project is useful for various IoT applications such as security cameras, monitoring systems, or remote photo capture.

Features:
  •	Capture high-quality photos using the ESP32-CAM (OV2640 module).
  •	Upload photos to Firebase Cloud Storage.
  •	Store photos temporarily on the ESP32 filesystem (LittleFS).
  •	Use Firebase Authentication for secure access.
  •	Configurable settings for photo capture and upload intervals.
  
Hardware Requirements:
  •	ESP32-CAM module (e.g., AI Thinker ESP32-CAM).
  •	Jumper wires (to connect the ESP32-CAM to your computer for programming).
  •	Micro-USB cable or FTDI adapter (for programming).
  
Software Requirements:
  •	Arduino IDE with ESP32 board support.
  •	Firebase project with Firebase Authentication and Firebase Storage enabled.
  •	Firebase ESP32 library installed in Arduino IDE.

Installation Instructions:
  1. Set up Firebase
    1.	Create a Firebase Project:
        • Go to Firebase Console.
        • Create a new project and set up Firebase Storage.
  2.	Generate Firebase API Key:
        • Go to Firebase Console > Project Settings > General > Web API Key.
 
  3.	Set up Firebase Authentication:
        • Go to Firebase Console > Authentication > Sign-in method > Enable Email/Password sign-in.
  4.	Obtain Firebase Storage Bucket ID:
        • Find your Firebase Storage bucket under Storage > Files. The bucket ID will look something like your-project-id.appspot.com.

  2. Install Arduino Libraries
    In the Arduino IDE, install the following libraries:
      •	Firebase ESP32: To interact with Firebase.
      •	ESP32 Camera: For capturing images with the ESP32-CAM.
      To install the libraries:
        1.	Open Arduino IDE.
        2.	Go to Sketch > Include Library > Manage Libraries.
        3.	Search for and install Firebase ESP32 and ESP32 Camera.

  3. Configure the Code
    1.	Clone or download this repository.
    2.	Open the project in the Arduino IDE.
    3.	In the code, update the following placeholders:
        •	ssid: Wi-Fi SSID.
        •	password: Wi-Fi password.
        •	API_KEY: Firebase API key from Firebase Console.
        •	USER_EMAIL: Firebase user email for authentication.
        •	USER_PASSWORD: Firebase user password for authentication.
        •	STORAGE_BUCKET_ID: Firebase Storage bucket ID.
 
  4. Configure the Camera
    Ensure the ESP32-CAM's pin configuration is set correctly. The provided code is set for the AI Thinker ESP32-CAM module using the OV2640 camera.

  5. Upload the Code
    1.	Connect the ESP32-CAM to your computer using a USB-to-serial adapter (if using).
    2.	Open the Arduino IDE and select the appropriate board: AI Thinker ESP32-CAM.
    3.	Select the correct COM port for your ESP32-CAM.
    4.	Upload the code to your ESP32-CAM module.

  6. Test the Setup
    Once the code is uploaded, the ESP32 will:
    •	Connect to Wi-Fi.
    •	Capture a photo using the ESP32-CAM.
    •	Save the photo to the internal LittleFS filesystem.
    •	Upload the photo to Firebase Storage.

  7. Monitor Firebase Storage
    Check your Firebase Storage bucket to see if the photos are being uploaded. You should find the images stored with filenames like photo1.jpg.

Code Walkthrough
  •	Wi-Fi Initialization: The ESP32 connects to Wi-Fi using the provided ssid and password.
  •	Camera Initialization: The OV2640 camera is initialized, and frames are captured in JPEG format.
  •	LittleFS: The photo is saved to the internal filesystem (LittleFS) before being uploaded to Firebase Storage.
  •	Firebase Authentication: The user logs in using the Firebase email and password.
  •	Firebase Storage Upload: After capturing the photo, the image is uploaded to Firebase Storage with the MIME type image/jpeg.
  
Troubleshooting
  •	Wi-Fi Connection Issues: Ensure your Wi-Fi credentials are correct and the ESP32-CAM is within range.
  •	Camera Issues: Make sure the correct camera pins are set. If using a different ESP32-CAM model, check the pinout and modify the pin configuration accordingly.
  •	Firebase Authentication Issues: Verify that Firebase Authentication is enabled and the user credentials are correct.

Future Improvements
  •	Image Resolution and Quality: Adjust the camera settings for higher resolution or different compression settings.
  •	Image Capture on Motion Detection: Implement a motion detection system to capture images when motion is detected.
  •	Web Dashboard: Build a simple web interface to display the uploaded images from Firebase.


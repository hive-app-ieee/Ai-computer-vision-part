# Ai-computer-vision-part

 ## Face Recognition Attendance System
This project implements a face recognition attendance system designed to capture and record the entry and exit times of individuals. Here's a brief overview of how it works:

Features
Face Capture: The system captures an image of the person when they enter the premises.
Name Recording: The individual's name is recorded and linked with the captured image.
Database Storage: All details, including the name, entry time, and exit time, are stored in a database for record-keeping and further analysis.
Time Logging: The system accurately logs the time of entry and exit for each individual, ensuring precise attendance tracking.
How It Works
Image Capture: When a person enters, the system captures their image using a camera.
Name Entry: If the person is new, the system prompts the user to input their name.
Database Update: The captured face encoding, name, entry time, and exit time are stored in the database.
Exit Tracking: When the person exits, the system updates the database with the exit time.
API Implementation and Documentation
The system is built as a RESTful API using Flask. Below is the documentation of the available endpoints:

POST /check_in_or_out
This endpoint handles checking in and out of individuals based on their face recognition.

Request:
Method: POST
Content-Type: multipart/form-data
Parameters:
image (required): The captured image of the individual.
name (required only for new individuals): The name of the individual for first-time registration.
Response:
200 OK: The individual successfully checked in or out.
400 Bad Request: Missing required parameters or no face found in the image.
500 Internal Server Error: An error occurred while processing the image or interacting with the database.

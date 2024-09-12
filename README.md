# Face Recognition Attendance System



This project implements a face recognition attendance system designed to capture and record the entry and exit times of individuals. Below is an overview of the system's key features, architecture, and API documentation.

## Features
- **Face Capture**: Captures an image of the individual upon entry.
- **Name Recording**: Records and links the individual's name with their captured image.
- **Database Storage**: Stores details including the name, entry time, and exit time in a database for future analysis.
- **Time Logging**: Accurately logs entry and exit times for each individual, ensuring precise attendance tracking.

## How It Works
1. **Image Capture**: When a person enters, the system captures their image using a camera.
2. **Name Entry**: If the individual is new, the system prompts the user to input their name.
3. **Database Update**: The captured face encoding, name, entry time, and exit time are stored in the database.
4. **Exit Tracking**: When the individual exits, the system updates the database with the exit time.

---

## Project Structure
The project follows a well-organized structure, ensuring clean code separation and scalability.


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




---

## API Implementation and Documentation

The system is built as a RESTful API using Flask. Below is the documentation of the available endpoints:

### POST `/check_in_or_out`

This endpoint handles the check-in and check-out process of individuals based on their face recognition.

- **Method**: `POST`
- **Content-Type**: `multipart/form-data`
- **Parameters**:
  - `image` (required): The captured image of the individual.
  - `name` (required only for new individuals): The name of the individual for first-time registration.
  
- **Response**:
  - `200 OK`: The individual successfully checked in or out.
  - `400 Bad Request`: Missing required parameters or no face found in the image.
  - `500 Internal Server Error`: Error processing the image or interacting with the database.

**Example Request**:
```bash
POST /check_in_or_out
Form Data:
- name: [shahdelghitani] (Only for first-time registration)
{
  "message": "shahd elghitani checked in successfully"
}
GET /attendance?name=shahdelghitani
{
  "entry_time": "2024-09-12 08:00:00",
  "exit_time": "2024-09-12 17:00:00"
}


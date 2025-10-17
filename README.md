
# ATM Security System with Facial Recognition

A **Tkinter-based ATM system** with **facial recognition**, **OTP verification**, and basic banking functionalities (withdraw, deposit, balance inquiry). This project integrates **Python**, **OpenCV**, **face_recognition**, and **Twilio API** for secure transactions.


## Features

* **User Enrollment**

  * Register with name, password, phone number, and face image.
  * Automatic face capture using webcam.
  * Passwords are securely hashed with **PBKDF2-HMAC-SHA256**.

* **OTP Verification**

  * OTP sent to the user’s phone number before sensitive actions (enrollment and login) using **Twilio API**.

* **Facial Recognition Login**

  * User login requires **name, password, phone number**, and successful **face verification**.
  * Ensures high security and prevents unauthorized access.

* **Banking Functionalities**

  * **Withdraw**: Deduct amount from account if balance is sufficient.
  * **Deposit**: Add amount to account.
  * **Balance Check**: Shows current balance with an alert if balance < 1000.
  * **Logout**: Ends session and returns to main menu.

* **User Data Management**

  * User info stored securely in a **CSV file**.
  * Faces stored in a dedicated **faces directory**.
  * Embeddings cached for fast face verification.

* **User-Friendly GUI**

  * Modern interface built with **Tkinter**.
  * Responsive buttons with hover effects.
  * Full-screen secure application.


## Technologies Used

* Python 3.x
* Tkinter (GUI)
* OpenCV (Webcam capture and image processing)
* face_recognition (Face detection & embeddings)
* Twilio API (OTP SMS verification)
* PIL/Pillow (Image handling)
* CSV (User data storage)
* hashlib (Secure password hashing)


## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/ATM-Facial-Recognition.git
cd ATM-Facial-Recognition
```

2. Install dependencies:

```bash
pip install opencv-python face_recognition Pillow twilio
```

> **Note:** `face_recognition` requires `dlib`. For installation issues, refer to [face_recognition installation guide](https://github.com/ageitgey/face_recognition#installation).

3. Create required directories (if not auto-created):

```bash
mkdir faces
```

4. Replace **Twilio credentials** in the code with your own:

```python
TWILIO_ACCOUNT_SID = 'YOUR_SID'
TWILIO_AUTH_TOKEN = 'YOUR_AUTH_TOKEN'
TWILIO_PHONE_NUMBER = 'YOUR_TWILIO_NUMBER'
```

---

## Usage

1. Run the application:

```bash
python atm_face_recognition.py
```

2. **Main Menu**

   * Enroll a new user
   * Login for existing users
   * Exit application

3. **Enrollment Process**

   * Enter name, password, and phone number.
   * Verify OTP sent via SMS.
   * Capture face using webcam.
   * User successfully added with hashed password and face embedding.

4. **Login Process**

   * Enter credentials and registered phone number.
   * Verify OTP sent via SMS.
   * Perform facial recognition using webcam.
   * Access dashboard with banking functionalities.


## Security Features

* **Secure password storage** using salt and hashing.
* **OTP verification** for additional security.
* **Facial recognition login** prevents unauthorized access.
* **Balance alert** when funds are low.



## File Structure

```
ATM-Facial-Recognition/
│
├── faces/              # Stores captured face images
├── user_data.csv       # Stores user info and hashed passwords
├── atm_face_recognition.py  # Main application
└── README.md
```



## Future Enhancements

* Add **admin panel** for managing users.
* Integrate **transaction history** for each user.
* Support **multiple face captures** per user for better accuracy.
* Add **voice alerts or email notifications** for transactions.




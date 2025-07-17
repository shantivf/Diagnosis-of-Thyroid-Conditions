WEBSITE IMPLEMENTATION
Web-based system for diagnosing thyroid conditions using CNN

PREREQUISITES

	REQUIRED SOFTWARE:

	Visual Studio Code (code editor).
	Python 3.6.8 (preferably the version used in training).
	Modern web browser (Chrome, Firefox, Edge)
	
	BOOKSTORES AND PROJECT DEPENDENCIES
	
	Flask
	TensorFlow
	Keras
	NumPy
	Pillow
	Work
	h5py
	Gunicorn
	Gevent

2. PROJECT STRUCTURE

The project contains the following folder and file structure:
thyroid-web-app/
│
├── app.py
├── requirements.txt
├── Procfile
├── models/
│ └── EfficientNetB3.h5
├── uploads/
├── templates/
│ ├── import.html
│ └── index.html
├── static/
│ ├── css/
│ │ └── main.css
│ ├── js/
│ │ └── main.js
│ └── images/
│     └── wallpaper.jpg
	
3. STEP-BY-STEP INSTALLATION

	Download the project

	Install and run Visual Studio Code
	Open a terminal (Ctrl + ñ o Ctrl + ~)and navigate to the folder where you want to save the project.
	Zip file and open the folder in VS Code .

	Install dependencies

	In the virtual environment, run the following:
		pip install -r requirements.txt (in order to install the necessary libraries)
	
4. BACKEND STRUCTURE (app.py)

The file app.pyis the heart of the backend and contains:
	Loading the trained model (EfficientNetB3.h5).
	Pre-processing of images.
	Routes to load the main page (/) and receive the image (/predict).
	Classification into three thyroid conditions:
		Normal thyroid Identified
		Benign thyroid Identified
		Malignant thyroid Identified.
	
5. USER INTERFACE (FRONTEND)

templates/import.html
	HTML main template with Bootstrap.
	Custom background and institutional header.
templates/index.html
	Inherits import.html.
	Allows you to upload images in .jpg , .jpeg , .png formats.
	Predict button to start inference.
	
6. STYLES AND SCRIPTS

static/css/main.css
	Styles for the button, image preview and loader.
static/js/main.js
	JavaScript code for:
		Preview the image.
		Send the image to the Flask server with AJAX.
		Display the result on the screen.
	
7. LOCAL EXECUTION OF THE PROJECT

In the terminal, inside the root folder of the project, run: python app.py
Flask server and display: Running on http://127.0.0.1:5000/
	Open your browser and visit: http://localhost:5000
	Upload a thyroid ultrasound image.
	Press Predict and you will get a diagnosis: Normal thyroid Identified, Benign thyroid Identified or Malignant thyroid Identified.
	
8. TECHNICAL CONSIDERATIONS

	The .h5 model must match the architecture expected by model_predict ( ).
	preprocess_input function must be correct for EfficientNetB3.
	The image must have size (300, 300), because that is how the model was trained.
	The model must be located in models /EfficientNetB3.h5.
	
9. KEY FILES

File / Folder	          Description
app.py	                  Main logic of the Flask server.
templates/	          HTML templates .
static/	                  Resources such as CSS, JS and images.
uploads/	          Folder where uploaded images are saved.
models/	                  Contains the trained model .h5 
requirements.txt	  List of dependencies to install.
Procfile	          Required for deployment.

	
10. FINAL TEST

Once the system is running correctly, verify that:
	An ultrasound image can be uploaded.
	The image is displayed correctly on the screen.
	An accurate diagnosis is obtained as: Normal thyroid Identified, Benign thyroid Identified or Malignant thyroid Identified.

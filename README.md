
# Regex Matcher Web App

## Overview

This is a simple web application built using **Flask** that replicates the core functionality of [regex101.com](https://regex101.com/). The app allows users to input a test string and a regular expression (regex) to display all matching patterns. Additionally, there's an email validation feature where users can check if an email address is valid using regex.

## Features

- **Regex Matching**: Users can input a test string and a regex pattern, and the app will display all the matches found.
- **Email Validation**: A separate page allows users to validate email addresses using regex.
- **Error Handling**: If the user enters an invalid regex pattern, the app handles the error gracefully and informs the user.
- **Responsive Design**: The app is centered with a clean, user-friendly interface that is styled using basic CSS.

## Project Structure

```plaintext
.
├── app.py                # The main Flask application
├── templates
│   ├── index.html        # Template for the main regex matcher page
│   ├── email.html        # Template for the email validation page
├── static
│   └── style.css         # CSS file for styling the application
└── README.md             # Project documentation
```

## Setup Instructions

To set up and run the project locally, follow the instructions below:

### 1. Clone the Repository

First, clone the repository to your local machine using:

```bash
git clone https://github.com/your-repo/regex-matcher-webapp.git
cd regex-matcher-webapp
```

### 2. Set Up a Virtual Environment

It’s recommended to use a virtual environment to manage dependencies. Set up and activate a virtual environment:

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment (Windows)
venv\Scripts\activate

# Activate the virtual environment (Mac/Linux)
source venv/bin/activate
```

### 3. Install Dependencies

Install the required Python packages using the `requirements.txt` file:

```bash
pip install Flask
```

### 4. Run the Application

Run the Flask application:

```bash
python app.py
```

The app should now be running locally at `http://127.0.0.1:5000/`.

### 5. Access the Application

Open your browser and go to the following URLs:

- **Regex Matcher**: `http://127.0.0.1:5000/`
- **Email Validation**: `http://127.0.0.1:5000/email`

## Project Components

### 1. `app.py`

This is the core Flask file that defines the routes for the web application:
- `/`: Displays the regex matching form.
- `/results`: Handles the form submission and displays the matched regex patterns.
- `/email`: Displays the email validation form.
- `/validate_email`: Handles email validation and returns the result.

### 2. Templates

- **`index.html`**: Contains the form where users can input the test string and regex pattern, as well as the results.
- **`email.html`**: A separate page for email validation with a form and result display.

### 3. CSS Styling

The app uses a simple CSS file located in the `static/style.css` to style the layout, center the content, and add colors and spacing for a clean look.

## Example Usage

### Regex Matcher
1. Open the app at `http://127.0.0.1:5000/`.
2. Input a test string and a regex pattern.
3. Click on "Match" to see the results.

**Example:**
- Test String: `I have 2 apples and 10 bananas.`
- Regex Pattern: `\d+`
- Matches: `['2', '10']`

### Email Validation
1. Navigate to `http://127.0.0.1:5000/email`.
2. Input an email address and click "Validate".

**Example:**
- Email: `test@example.com`
- Result: `Valid`

## Screenshots

### Regex Matcher Page
![Screenshot 2024-10-19 150139](https://github.com/user-attachments/assets/9936e07f-ce4f-477d-a132-5d5327df4ec4)

### Email Validation Page
![Screenshot 2024-10-19 150228](https://github.com/user-attachments/assets/98f77d9b-94ed-4ee2-86c5-c3217bd5d9e9)


## Deployment

### Deploying on AWS

If you'd like to deploy this app to the cloud using AWS, follow these steps:

1. **Set up an EC2 instance**:
   - Launch a new EC2 instance with the appropriate configurations.
   - SSH into the instance and install the required packages (Python, Flask).

2. **Install Flask**:
   ```bash
   sudo apt update
   sudo apt install python3-pip
   pip3 install Flask
   ```

3. **Transfer the project files**:
   - Use `scp` to copy your project files to the EC2 instance.
   ```bash
   scp -i your-key.pem -r /path/to/your/project ubuntu@your-ec2-ip:/home/ubuntu/
   ```

4. **Run the Flask app**:
   ```bash
   python3 app.py
   ```

5. **Access the app**:
   - You can now access the app using the public IP of your EC2 instance.

## Credits

This project is developed as a learning exercise for creating a web application using **Flask** and **Regular Expressions**.

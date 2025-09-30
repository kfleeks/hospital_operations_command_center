Hospital Operations Command Center
This project is a real-time, simulated dashboard application that provides a high-level overview of a hospital's operational status. Built with Python and Streamlit, it serves as a proof-of-concept for how data centralization and AI-powered analytics can be used to optimize hospital workflow and patient flow.
The application visualizes a dynamic command center, with data that updates every few seconds to mimic a live operational environment.
Features
The dashboard is organized into several key modules:
Key Performance Indicators (KPIs): A top-level summary of the most critical metrics, including:
Total Patient Count
Overall Bed Occupancy Percentage
Average Emergency Department (ED) Wait Time
Number of Operating Rooms (ORs) in Use
Emergency Department Live Status: A live, sortable table of patients currently in the ED, prioritized by acuity level. It displays their wait time and current status (e.g., "Waiting", "With Doctor").
Inpatient Ward Occupancy: A series of progress bars visually representing the current patient load in each hospital ward (ICU, Cardiology, etc.) relative to its total capacity.
AI-Powered Forecasts: A simulation of an AI engine's predictions for future operational needs, including:
Predicted patient admissions for the next shift.
Data-driven recommendations for nurse staffing levels to meet anticipated demand.
How It Works
This application is a self-contained simulation. It does not connect to any real hospital data or external APIs.
Data Generation: On startup, the script procedurally generates a set of initial data for patients, surgical procedures, and ward occupancy using Python's random library.
Simulation Loop: A while loop runs continuously. In each iteration, the HospitalSimulation.run_simulation_step() method is called. This method uses random probabilities to simulate events like new patient arrivals, patient discharges, and changes in surgery status.
Real-Time UI with Streamlit: After each simulation step, the user interface is re-rendered using Streamlit. Streamlit's components (metrics, dataframes, progress bars) are used to build the dashboard. The time.sleep(2) function creates a 2-second pause between updates, giving the dashboard its real-time feel.
Getting Started
Follow these instructions to run the application on your local machine.
Prerequisites
Python 3.7+
Installation
Clone the repository (or download the script):
git clone <your-repo-url>
cd <your-repo-directory>


Install the required Python libraries:
The application relies on Streamlit for the web interface and Pandas for data manipulation.
pip install streamlit pandas


Running the Application
Navigate to the project directory in your terminal.
Run the following command:
streamlit run hospital_streamlit_app.py


Streamlit will start a local web server and automatically open the application in your default web browser.
Code Structure
The hospital_streamlit_app.py script is organized into four main sections:
Static Data Configuration: Defines the constants for the simulation, such as ward names, capacities, and lists of possible patient names and procedures.
Data Generation Functions: A set of functions (generate_initial_patients, etc.) that create the initial state of the hospital when the app first starts.
HospitalSimulation Class: The core of the application. This class holds the hospital's state and contains the run_simulation_step method, which holds all the logic for updating the simulation over time.
Streamlit UI Layout: The display_dashboard function contains all the Streamlit code responsible for rendering the web interface, including titles, metrics, columns, and data tables.

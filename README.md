# Final-Project-
Final Project 
# Medicine Inventory Web App - Cambridge, MA
#### Video Demo: <https://youtu.be/URL_HERE> <!-- Replace with actual URL after upload -->
#### Description:

The Medicine Inventory Web App is a Flask-based web application designed to simulate and manage an inventory of specific medicines commonly available in pharmacies around Cambridge, Massachusetts. Users can view a pre-populated list of medicines (e.g., Aspirin, Ibuprofen), add stock to existing entries, and remove medicines from the inventory—all through a simple browser interface. This project fulfills the requirements of a Python programming course final project, showcasing web development skills with Flask while focusing on a practical, location-specific use case.

Inspired by the need to track medicine availability in a city like Cambridge, home to major institutions and a dense pharmacy network (e.g., CVS, Walgreens, Inman Pharmacy), this app simulates a static inventory based on typical over-the-counter medications. It uses an in-memory dictionary to store data, balancing simplicity with functionality, and provides a foundation for real-world extensions like connecting to pharmacy APIs.

### Files and Their Purposes

- **project.py**: The heart of the application, containing all logic and Flask configuration.
  - **`add_medicine(name, quantity)`**: Increases the quantity of a specified medicine, with validation to ensure it’s a known Cambridge medicine and quantity is valid.
  - **`remove_medicine(name)`**: Deletes a medicine from the inventory, returning success or failure.
  - **`get_inventory()`**: Returns a copy of the current inventory, preserving the original data.
  - **`main()`**: Initializes the Flask app, defines routes (`/`, `/add`, `/delete/<name>`), and runs the server with an embedded HTML template displaying the inventory.
- **test_project.py**: Unit tests for the three required functions using `pytest`, ensuring core logic works as expected.
- **requirements.txt**: Lists `flask` for the web framework and `pytest` for testing, installable via pip.

### Functionality and Features

The app launches at `http://localhost:5000`, presenting a dropdown of Cambridge-available medicines, a field to add stock, and a list of current inventory with pharmacy locations. Users can:
- **Add Stock**: Select a medicine (e.g., "Aspirin") and enter a quantity to increase its stock, with feedback on success or errors.
- **View Inventory**: See all medicines, their quantities, and where they’re available (e.g., "CVS Pharmacy, 624 Massachusetts Ave").
- **Delete**: Remove a medicine from the list via a link, simulating it being discontinued or sold out.

### Design Choices

Flask was chosen for its lightweight, beginner-friendly nature, aligning with the rubric’s web app suggestion. The inventory is pre-populated with five common medicines (Aspirin, Ibuprofen, Acetaminophen, Loratadine, Omeprazole) and their typical Cambridge pharmacy locations, based on general knowledge of chain and local pharmacies like CVS, Walgreens, and Inman Pharmacy. A real-time database or API integration was avoided to keep the scope manageable, using a dictionary instead—data resets on server restart, a deliberate simplification.

The UI uses a dropdown for medicine selection to enforce the Cambridge-specific list, reducing errors compared to free text input. Validation in `add_medicine` rejects unknown medicines or invalid quantities, enhancing usability. The `get_inventory` function returns a copy to prevent accidental data corruption, reflecting good practice. Deletion uses a GET request for simplicity, though a POST would be safer in production—I prioritized ease of use here.

### Usage Instructions

1. **Prerequisites**: Python 3 with pip installed.
2. **Setup**: Save `project.py`, `test_project.py`, and `requirements.txt` in a `project` directory.
3. **Install Dependencies**: In a terminal, navigate to the directory and run:

This project uses keystroke timing data to build a machine learning model that can identify users based on how they type a known password (secure123). Each user typed the same password multiple times, and their typing patterns (dwell and flight times) were recorded in CSV files.

 Project Structure
bash
Copy
Edit
keystroke-authentication/
│
├── data/
│   ├── Sagnik_Patra.csv
│   ├── Ankush_Ramteke.csv
│   ├── Anannya_Saha.csv
│   └── Annan_Sadr.csv
│
├── keystroke_model.py       # Main script for training and prediction
├── label_encoder.pkl        # Saved label encoder (auto-generated)
├── keystroke_model.h5       # Trained model (auto-generated)
├── README.md
 Features Used
Hold Time (Dwell Time): How long each key is held.

Flight Time: Time between key release and next key press.

Each sample contains timing info for the sequence secure123.

 How to Run
 1. Prepare Your Data
Ensure you have:

One CSV file per user, named clearly (e.g., Sagnik_Patra.csv)

Each file should contain multiple entries (e.g., 6 samples per user) of keystroke timing for the word secure123.

 2. Run the Script
bash
Copy
Edit
python keystroke_model.py
 Input Flow
You will be prompted to:

Enter the number of users (e.g., 4)

Enter the path for each user’s CSV file

After training, provide a test CSV file (from a user typing secure123) to predict who it is.

Example:

mathematica
Copy
Edit
Enter number of users (e.g. 4): 4
Enter CSV path for user 1: C:\path\to\Sagnik_Patra.csv
Enter CSV path for user 2: C:\path\to\Anannya_Saha.csv
...
Enter path to the keystroke CSV for prediction: C:\path\to\test_sample.csv
 Output
After prediction, the script will print:

bash
Copy
Edit
Predicted User: Sagnik_Patra
 Dependencies
Python 3.7+

TensorFlow

NumPy

scikit-learn

pandas

You can install all dependencies using:

bash
Copy
Edit
pip install -r requirements.txt
 Model
Built using a deep neural network (DNN) with:

Multiple dense layers

ReLU activations

Dropout for regularization

Accuracy depends on consistent typing patterns and quality of data

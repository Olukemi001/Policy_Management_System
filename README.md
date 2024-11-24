# Policy_Management_System
This is a Python-based application designed to manage insurance policyholders, products, and payments. It provides essential functionality for registering policyholders, managing their accounts, handling payments, and updating insurance products. This project emphasizes modular design and includes robust error handling for enhanced reliability.

# Policy Management System README

## Overview
The **Policy Management System** is a Python-based project that models policyholders, products, and payments for an insurance system. The system includes functionality for managing policyholder accounts, processing payments, and managing insurance products.
Key features include account suspension/reactivation, payment processing with reminders and penalties, and product creation and management. The project also includes a demonstration script (main.ipynb/main.py) that showcases the system's capabilities by simulating real-world scenarios with sample policyholders and products.

This repository includes Python code written in Jupyter notebooks and converted to `.py` files for module-based imports. Error handling has been implemented throughout to ensure robustness and provide meaningful feedback during execution.

---

## Repository Structure

```plaintext
├── policyholders.ipynb   # Jupyter notebook for Policyholder class
├── products.ipynb        # Jupyter notebook for Product class
├── payments.ipynb        # Jupyter notebook for Payment class
├── main.ipynb            # Demonstrates the policy management system
├── convert_ipynb_to_py.ipynb  # Script to convert .ipynb files to .py
├── policyholders.py      # Converted Policyholder module
├── products.py           # Converted Product module
├── payments.py           # Converted Payment module
├── main.py               # Main script demonstrating functionality
```

---

## Features

### 1. **Policyholders Management**
- **Register Products:** Policyholders can register for active products.
- **Suspend Accounts:** Suspend policyholders who fail to meet requirements.
- **Reactivate Accounts:** Reactivate policyholders when necessary.
- **Display Details:** View account information, including status and registered products.

### 2. **Product Management**
- **Create Products:** Define insurance products with attributes like ID, name, and premium.
- **Update Products:** Update product details such as name and premium.
- **Suspend Products:** Mark products as inactive.

### 3. **Payment Management**
- **Process Payments:** Ensure payments are recorded for specific policyholders and products.
- **Send Reminders:** Notify policyholders of pending payments.
- **Apply Penalties:** Add penalties for late payments.

### 4. **Demonstration**
- Demonstrates the system by creating:
  - **Four products**
  - **Three policyholders**
  - Processes payments and displays account details.

---

## Getting Started

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook (optional, for viewing `.ipynb` files)

### Installation
Copy the Policy_Management_System folder into the desired location on your system. Unzip the folder and open the files in Jupyter Notebook

## Running the Project

### Step 1: Convert Notebooks to Python Files
If you need to generate `.py` files from the `.ipynb` notebooks, use the provided conversion script:

```python
# In convert_ipynb_to_py.ipynb
import nbformat
from nbconvert import PythonExporter
import os

# Specify your directory
notebook_dir = "<path-to-notebooks>"

# Run the script to convert notebooks
```

### Step 2: Run the Main Program
The `main.ipynb` script demonstrates the functionality of the system:

---

## Error Handling

### Policyholders
- **Invalid ID:** Raises `ValueError` if the ID is not an integer.
- **Invalid Name:** Raises `ValueError` if the name is empty or not a string.
- **Invalid Email:** Raises `ValueError` for invalid email formats.

### Products
- **Invalid ID:** Raises `ValueError` if the product ID is not an integer.
- **Invalid Name:** Raises `ValueError` if the product name is empty or not a string.
- **Invalid Premium:** Raises `ValueError` if the premium is not a positive number.

### Payments
- **Invalid Policyholder/Product:** Ensures associated objects are valid.
- **Invalid Amount:** Raises `ValueError` if the payment amount is not positive.
- **Duplicate Payment:** Prevents processing an already-paid transaction.
- **Penalty Application:** Ensures penalties are valid and applied only to unpaid transactions.

---

## Example Outputs
### Policyholder Registration
```plaintext
Kemi registered for product: Health Insurance
Cannot register. Policyholder Modupe is suspended.
```

### Payment Processing
```plaintext
Payment of 100000 for product Health Insurance by Kemi processed.
Reminder: Payment of 400000 is due for Modupe.
```

### Policyholder Details
```plaintext
Policyholder ID: 1, Name: Kemi, Status: Active, Registered Products: - Health Insurance
Policyholder ID: 2, Name: Modupe, Status: Suspended, Registered Products: No products registered.
```

---

## Troubleshooting

### `ModuleNotFoundError`
If you encounter a `ModuleNotFoundError` when importing modules in `main.ipynb` as seen below:

![image](https://github.com/user-attachments/assets/6fb28d7d-7924-42c1-b874-6e9593db88b1)

Ensure you:
1. Run the `convert_ipynb_to_py.ipynb` script.
2. Confirm that `.py` files are in the same directory as `main.py`.
3. Add the directory to your `PYTHONPATH` if necessary:
   ```python
   import sys
   sys.path.append("<path-to-directory>")
   ```

### General Errors
The system uses `try-except` blocks to catch and display meaningful error messages. Refer to the error output to identify and resolve issues.

---

## Conclusion
This project demonstrates a simple yet functional policy management system using Python. The separation of classes into modules ensures modularity and reusability, while error handling enhances reliability.


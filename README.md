
# Used Cars Database Normalization Project

This project involves creating and normalizing a PostgreSQL database using a dataset of used cars.

## Setup

1. Clone this repository to your local machine.

    ```bash
    git clone https://github.com/yourusername/used-cars-db.git
    ```

2. Navigate to the project directory.

    ```bash
    cd used-cars-db
    ```

3. Install the required Python packages. It is recommended to use a virtual environment for this.

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
    pip install -r requirements.txt
    ```

4. Ensure you have a running PostgreSQL instance. Update the database connection string in the script if necessary.

5. Run the script.

    ```bash
    python3 script.py  # On Windows, use 'python script.py'
    ```

## Project Overview

The project performs the following tasks:

1. **Data Loading**: The script starts by loading a dataset containing used car data.

2. **Data Cleaning**: The following cleaning steps are performed:
    - Stripping of trailing and leading whitespaces.
    - Removal of punctuation marks.
    - Standardization of date formats.

3. **Data Normalization**: The cleaned data is then normalized according to the rules of First Normal Form (1NF), Second Normal Form (2NF), and Third Normal Form (3NF). This involves eliminating redundant data, ensuring data dependencies make sense, and others.

4. **Database Population**: After normalization, the data is loaded into a PostgreSQL database. This involves creation of the necessary tables, and insertion of the data into the tables.

---

Remember to replace `https://github.com/yourusername/used-cars-db.git` with the URL of your actual GitHub repository, and `script.py` with the actual name of your script file.
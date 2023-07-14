
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

4. **Set up PostgreSQL**: You need a running PostgreSQL instance to which the script can connect. Here's a detailed explanation of this step:

    - **Install PostgreSQL**: If not already installed, you need to install PostgreSQL on your machine. The installation steps can vary by operating system. You can refer to the official PostgreSQL documentation for detailed instructions.

    - **Create a database**: After installation, create a new PostgreSQL database that will be used to store the normalized car data. You can do this through the `psql` command line interface, or using a graphical interface like pgAdmin.

    - **Create a .env file**: The script uses the `os` and `dotenv` Python libraries to securely handle database credentials. These credentials are read from a file named `.env` in the project directory. This file is not included in the repository for security reasons, and you need to create it manually.
        - In the project directory, create a new file named `.env`.
        - Inside this file, add your PostgreSQL credentials and the name of the database you created in the following format:

            ```bash
            DB_USER=your_postgres_username
            DB_PASSWORD=your_postgres_password
            DB_NAME=your_database_name
            ```

        - Replace `your_postgres_username`, `your_postgres_password`, and `your_database_name` with your actual PostgreSQL username, password, and the name of the database you created.

    - **Update the database connection string**: Open the Python script in a text editor. Look for the line where the database connection string is defined. It should look something like this:

        ```python
        engine = create_engine(f"postgresql+psycopg2://{DB_USER}:{DB_PASSWORD}@localhost/{DB_NAME}")
        ```

        If your PostgreSQL server is not running on the local machine, or if it's running on a non-default port, you need to update this connection string accordingly.

5. **Running the Jupyter Notebook**:

   The project is contained within a Jupyter Notebook (.ipynb file). If you are not familiar with Jupyter Notebook, it is an open-source web application that allows you to create and share documents that contain both code (e.g., python or R) and rich text elements (paragraphs, equations, figures, links, etc...). Here's how to run it:

   - **Install Jupyter**: If you don't have Jupyter installed on your system, you will need to install it. Jupyter is included in the Anaconda distribution of Python. You can install Anaconda following the instructions provided on their [official website](https://www.anaconda.com/products/distribution). Alternatively, you can install Jupyter independently by running the command `pip install jupyter` in your terminal or command prompt.

   - **Open the Notebook**: Navigate to the directory containing the Jupyter Notebook file in the terminal or command prompt. You can then start the Jupyter Notebook application by running the command `jupyter notebook`. This will start the server and open a new page in your web browser with a list of the available notebooks in the current directory.

   - **Run the Code**: Click on the notebook file (with the `.ipynb` extension) to open it. The notebook will open in a new tab. It is divided into cells, some of which contain text, while others contain Python code. You can run the cells in order by clicking on the cell and then clicking on the 'run' button at the top of the page, or by pressing `Shift + Enter`. Ensure to run all cells in order, as some cells might depend on the results of previous cells. 

   - **Adjust the Code**: If needed, you can edit any of the code cells by clicking on them and making your changes. This might be necessary to adjust the database connection string, correct any errors, or adapt the code to a different dataset.

## Project Overview

The project performs the following tasks:

1. **Data Loading**: The script starts by loading a dataset containing used car data.

2. **Data Cleaning**: The following cleaning steps are performed:
    - Stripping of trailing and leading whitespaces.
    - Removal of punctuation marks.
    - Standardization of date formats.

3. **Data Normalization**: The cleaned data is then normalized according to the rules of First Normal Form (1NF), Second Normal Form (2NF). 

4. **Database Population**: After normalization, the data is loaded into a PostgreSQL database. This involves creation of the necessary tables, and insertion of the data into the tables.

Consult the file "to_do.ipynb" for specific notes on normalization and standardization. 
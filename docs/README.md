# DataProcessingLibrary

## Overview

**DataProcessingLibrary** is a Python library designed for efficient data importation, preprocessing, saving, and visualization. It simplifies common data processing tasks, making it easier for data analysts and machine learning practitioners to handle their datasets.

## Features

- Import data from CSV, JSON, and Excel formats.
- Clean data by removing duplicates and handling missing values.
- Normalize data using various methods (min-max scaling, standardization).
- Create new features through feature engineering.
- Save the state of your data processing workflow.
- Visualize data using various types of plots (scatter, histogram, bar, line, pie).

## Installation

To install and use this library, follow these steps:

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd DataProcessingLibrary
   ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

Note: Ensure you have pandas, matplotlib, and openpyxl installed, as they are required for the library to function properly.

## Usage

### Importing Data

You can import data from various formats as shown below:

```python
from src.my_data_import_lib import DataImporter

# Import data from a CSV file
data_csv = DataImporter.from_csv('data/sample_data.csv')

# Import data from a JSON file
data_json = DataImporter.from_json('data/sample_data.json')

# Import data from an Excel file
data_excel = DataImporter.from_excel('data/sample_data.xlsx')
```

## Preprocessing Data

The library provides functionalities to clean and normalize your data:

```python
from src.my_data_preprocessing_lib import DataPreprocessor
from src.my_data_saving_lib import DataSaver

# Create a DataSaver instance to save the processed data
data_saver = DataSaver('data/saved_data.json')

# Initialize the DataPreprocessor with data and DataSaver
preprocessor = DataPreprocessor(data_csv, data_saver)

# Clean the data (remove duplicates and missing values)
cleaned_data = preprocessor.clean_data()

# Normalize the data using min-max scaling
normalized_data = preprocessor.normalize_data(method='minmax')
```

## Feature Engineering

You can create new features from existing ones as follows:
```python
# Define a simple feature engineering function
def multiply_by_two(entry):
    return entry['A'] * 2 if entry['A'] is not None else None

# Add a new feature 'D' to the dataset
new_feature_data = preprocessor.feature_engineering('D', multiply_by_two)
```

## Visualizing Data

Visualize your data using various plot types:
```python
from src.my_visualization_lib import DataVisualizer

# Create a DataVisualizer instance with the normalized data
visualizer = DataVisualizer(normalized_data)

# Visualize the data using a scatter plot
visualizer.visualize_data('A', 'C', plot_type='scatter')

# Visualize the data using a histogram
visualizer.visualize_data('A', plot_type='histogram')

# Visualize the data using a bar chart
visualizer.visualize_data('A', plot_type='bar')
```

## Running Tests

To ensure the functionality of the library, you can run the provided unit tests:

1. Navigate to the tests directory:

```bash
cd tests
```

2. Running the tests using:
```bash
python -m unittest discover
```

## Contributing
Contributions to the DataProcessingLibrary are welcome! If you have suggestions for improvements or new features, feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

## Contact
For any inquiries or feedback, please reach out via email at your-email@example.com.

Thank you for using DataProcessingLibrary! We hope it helps you efficiently manage your data processing tasks.

```javascript
### Notes:
- Replace `<repository-url>` with the actual URL of your repository.
- Update the contact email with your actual email address.
- If you have a `requirements.txt` file or other license information, ensure to include them in your repository.

This `README.md` provides clear instructions and insights into how to effectively use your library, making it easier for others to understand and contribute. Enjoy your coding journey!
```
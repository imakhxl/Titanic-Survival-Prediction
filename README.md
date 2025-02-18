# Titanic Survival Prediction Using Machine Learning

This project aims to predict the survival of passengers aboard the Titanic using the **Random Forest Classifier**. By analyzing various features such as age, gender, ticket class, and more, the model attempts to determine the likelihood of survival with high accuracy.

---

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Data Preprocessing](#data-preprocessing)
- [Modeling](#modeling)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

---

## Overview
The **Titanic Survival Prediction** project uses supervised learning to classify passengers as either 'Survived' or 'Not Survived'. This is achieved by training a model on the Titanic dataset, a classic dataset used for binary classification.

The main steps involved in this project include:
1. Data Cleaning and Exploration
2. Feature Engineering (including Age Grouping and Title Extraction)
3. Data Transformation and Encoding
4. Model Training using **Random Forest Classifier**
5. Evaluation and Predictions

---

## Dataset
The dataset is obtained from the [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic/data). It consists of two CSV files:
- `train.csv`: Used for training the model.
- `test.csv`: Used for making predictions.

**Target Variable:** `Survived` (0 = No, 1 = Yes)

---

## Features
The dataset includes the following features:
- `PassengerId`: Unique ID for each passenger
- `Pclass`: Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd)
- `Name`: Passenger's name
- `Sex`: Gender of the passenger
- `Age`: Age of the passenger
- `SibSp`: Number of siblings/spouses aboard
- `Parch`: Number of parents/children aboard
- `Ticket`: Ticket number
- `Fare`: Fare paid for the ticket
- `Cabin`: Cabin number
- `Embarked`: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

---

## Data Preprocessing
### 1. Title Extraction:
- Extracted titles from passenger names to better understand social status and grouping.
- Titles were mapped to numerical values:
  - `Mr`: 1, `Miss`: 2, `Mrs`: 3, `Master`: 4, `Royal`: 5, `Rare`: 6

### 2. Age Grouping:
- Grouped ages into categories:
  - `Baby`, `Child`, `Student`, `Young Adult`, `Adult`, `Senior`
- Missing age values were filled based on the most common age group for each title.

### 3. Encoding and Mapping:
- `Sex` was mapped as: `male = 0`, `female = 1`
- `Embarked` was mapped as: `S = 1`, `C = 2`, `Q = 3`
- `Fare` values were binned into quartiles and encoded as `FareBand`

### 4. Feature Selection:
- Dropped irrelevant features like `Name`, `Ticket`, and `Cabin`
- Retained features:
  - `Pclass`, `Sex`, `AgeGroup`, `SibSp`, `Parch`, `FareBand`, `Embarked`, `Title`

---

## Modeling
The model used for prediction is the **Random Forest Classifier** because of its robustness and high accuracy in classification tasks.

- **Algorithm Used:** Random Forest
- **Library:** scikit-learn
- **Model Evaluation:**
  - Split data into training and validation sets
  - Evaluated using accuracy score
  - Achieved an accuracy of approximately **X%** (replace X with your result)

---

## Results
- The model demonstrated good accuracy and generalization on the validation set.
- The final predictions were saved in a CSV file named `resultfile.csv`.

---

## Installation
To set up the project locally:
1. Clone this repository:
    ```sh
    git clone https://github.com/your-username/titanic-survival-prediction.git
    cd titanic-survival-prediction
    ```
2. Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```

### Requirements
- Python 3.x
- Pandas
- NumPy
- scikit-learn
- Jupyter Notebook (optional for interactive exploration)

---

## Usage
1. Ensure all dependencies are installed.
2. Place the `train.csv` and `test.csv` files in the project directory.
3. Run the notebook or script to:
    - Train the model
    - Evaluate accuracy
    - Generate predictions in `resultfile.csv`
4. View the output using:
    ```python
    import pandas as pd
    result = pd.read_csv('resultfile.csv')
    print(result.head())
    ```

---

## Technologies Used
- **Programming Language:** Python
- **Libraries:** 
  - `Pandas` and `NumPy` for data manipulation
  - `scikit-learn` for modeling and evaluation
- **Algorithm:** Random Forest Classifier
- **Tools:** Jupyter Notebook for development and testing

---

## Contributing
Contributions are welcome! 
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
- [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic/data) for the dataset
- Inspiration from various data science communities and tutorials.

---

## Contact
- **GitHub:** [Your GitHub Username](https://github.com/your-username)
- **LinkedIn:** [Your LinkedIn Profile](https://www.linkedin.com/in/your-profile)

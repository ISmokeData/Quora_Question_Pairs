# Quora Question Pairs Duplicate Detection

This project aims to identify whether two questions from the Quora Question Pairs dataset are duplicates or not. It leverages advanced feature engineering techniques and machine learning models to achieve accurate classification.

## Table of Contents
- [Dataset](#dataset)
- [Features](#features)
  - [Token Features](#token-features)
  - [Length-Based Features](#length-based-features)
  - [Fuzzy Features](#fuzzy-features)
- [Technologies Used](#technologies-used)
- [Modeling](#modeling)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Improving Accuracy](#improving-accuracy)
- [Contributing](#contributing)
- [License](#license)

## Dataset
The dataset used for this project is the **Quora Question Pairs** dataset. It contains pairs of questions along with a label indicating whether they are duplicates.

## Features
Advanced features were engineered to improve model performance:

### Token Features
- **cwc_min**: Ratio of common words to the length of the smaller question.
- **cwc_max**: Ratio of common words to the length of the larger question.
- **csc_min**: Ratio of common stop words to the smaller stop word count.
- **csc_max**: Ratio of common stop words to the larger stop word count.
- **ctc_min**: Ratio of common tokens to the smaller token count.
- **ctc_max**: Ratio of common tokens to the larger token count.
- **last_word_eq**: 1 if the last word in both questions is the same, 0 otherwise.
- **first_word_eq**: 1 if the first word in both questions is the same, 0 otherwise.

### Length-Based Features
- **mean_len**: Mean of the lengths of the two questions (in words).
- **abs_len_diff**: Absolute difference between the lengths of the two questions.
- **longest_substr_ratio**: Ratio of the longest common substring length to the length of the smaller question.

### Fuzzy Features
- **fuzz_ratio**: Fuzzy ratio score from `fuzzywuzzy`.
- **fuzz_partial_ratio**: Partial ratio from `fuzzywuzzy`.
- **token_sort_ratio**: Token sort ratio from `fuzzywuzzy`.
- **token_set_ratio**: Token set ratio from `fuzzywuzzy`.

## Technologies Used
- **Python**
- **Pandas**, **NumPy** for data manipulation
- **BeautifulSoup** for text preprocessing
- **regex** for advanced text pattern matching
- **CountVectorizer** for text vectorization
- **fuzzywuzzy** for fuzzy string matching
- **XGBoost** and **RandomForest** for classification
- **Matplotlib**, **Seaborn** for data visualization

## Modeling
Two machine learning models were implemented and compared:

1. **XGBoost Classifier**
2. **RandomForest Classifier**

The models were evaluated based on accuracy, precision, recall, and F1-score.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/quora-duplicate-questions.git
   ```
2. Navigate to the project directory:
   ```bash
   cd quora-duplicate-questions
   ```
3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Ensure the dataset is placed in the correct directory.
2. Run the main script:
   ```bash
   python main.py
   ```
3. The results, including model performance and feature importance, will be displayed.

## Results
The project achieved high accuracy in detecting duplicate questions. XGBoost outperformed RandomForest in terms of precision and recall. Detailed metrics and visualizations can be found in the results folder.

## Improving Accuracy
If you want to further improve the accuracy of the model, you can consider the following techniques:
1. **Increase Data**: Use more data to train the model for better generalization.
2. **Increase RAM**: Utilize higher memory to handle larger datasets and complex computations.
3. **Cloud Platform**: Use cloud-based platforms like AWS, Google Cloud, or Azure for scalable resources.
4. **Incremental Learning**: Implement incremental learning techniques using libraries like Dask.
5. **Preprocessing**: Apply advanced preprocessing methods like stemming and lemmatization.
6. **Apply More Algorithms**: Experiment with additional algorithms like LightGBM, CatBoost, or neural networks.
7. **Create More Features**: Engineer new features that could capture deeper relationships between question pairs.
8. **Bag of Words Models**: Implement models like TF-IDF, Word2Vec, and TF-IDF weighted Word2Vec to enhance text representation.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request.

## License
This project is licensed under the MIT License.


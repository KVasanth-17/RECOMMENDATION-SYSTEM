# Movie Recommendation System Using SVD

*COMPANY*: CODTECH IT SOLUTIONS  

*NAME*: VASANTH KANDIBANDA  

*INTERN ID*: CT08DZ1238 

*DOMAIN*: MACHINE LEARNING  

*DURATION*: 8 WEEKS  

*MENTOR*: NEELA SANTOSH  

*DESCRIPTION OF THE TASK*: 

This project implements a **movie recommendation system** using the **Surprise** library’s **SVD (Singular Value Decomposition)** algorithm on the **MovieLens 100k dataset**. The system predicts personalized movie ratings for a given user and recommends top-rated movies the user has not yet watched. It is designed to demonstrate the practical application of collaborative filtering in recommendation systems, combining efficiency with accuracy.

---

## Project Workflow

The system follows these stages:

1. **Data Preparation**
2. **Model Training and Evaluation**
3. **Cross-Validation**
4. **Model Retraining**
5. **Recommendation Generation**

---

### 1. Data Preparation
- Loads the MovieLens 100k dataset using Surprise’s built-in loader.
- Retrieves mapping of movie IDs to movie titles from the dataset file `u.item`.
- Stores movie title information in a dictionary for easy display of recommendations.
- Validates dataset presence and handles missing files gracefully.

---

### 2. Model Training and Evaluation
- Splits the dataset into training (75%) and testing (25%) sets.
- Uses **SVD (Singular Value Decomposition)** for collaborative filtering, which efficiently factors the user-item rating matrix into latent factors.
- Trains with **100 latent factors** over **20 epochs** to balance prediction accuracy and computational performance.
- Evaluates performance using:
  - **RMSE (Root Mean Squared Error)**
  - **MAE (Mean Absolute Error)**
- Prints metrics for performance assessment.

---

### 3. Cross-Validation
- Performs **5-fold cross-validation** to validate model robustness.
- Computes RMSE and MAE scores for each fold.
- Plots error metrics for visualization of consistency across folds. This helps understand the model’s stability across different subsets of data.

---

### 4. Retraining on Full Dataset
- Retrains the model on the complete dataset to leverage all available data.
- This step ensures that recommendations benefit from the entire dataset and not just the training split, improving prediction quality.

---

### 5. Generating Recommendations
- Identifies movies the user has not rated yet.
- Predicts ratings for all unrated movies using the trained model.
- Sorts predictions in descending order of rating and selects the top-N recommendations.
- Outputs recommendations as a Pandas DataFrame containing:
  - Rank
  - Movie Title
  - Item ID
  - Predicted Rating
- Ensures user-friendly presentation of results.

---

### Visualization
The model generates a plot displaying RMSE and MAE across cross-validation folds, offering visual insight into the model’s prediction stability and performance.

---

### Conclusion
This project demonstrates a practical application of **collaborative filtering** with matrix factorization. The SVD-based recommendation system efficiently predicts personalized ratings and produces relevant recommendations. Its modular design allows for easy extension, such as:
- Experimenting with other algorithms
- Using different datasets
- Adding advanced evaluation metrics

This provides a solid foundation for building more advanced recommendation systems and is a useful reference for anyone interested in recommender system development.

*OUTPUT*:

<img width="573" height="602" alt="Image" src="https://github.com/user-attachments/assets/e46c1a55-8025-465c-945b-f20ddad3ac91" />

| Rank | Movie Title                       | Item ID | Predicted Rating |
| ---- | --------------------------------- | ------- | ---------------- |
| 1    | Star Wars (1977)                  | 50      | 5.0000           |
| 2    | Raiders of the Lost Ark (1981)    | 258     | 4.9992           |
| 3    | Contact (1997)                    | 127     | 4.9958           |
| 4    | Terminator 2: Judgment Day (1991) | 181     | 4.9915           |
| 5    | Usual Suspects, The (1995)        | 300     | 4.9891           |


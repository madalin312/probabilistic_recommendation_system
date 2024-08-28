# probabilistic_recommendation_system

# Recommendation System using Hierarchical Poisson Factorization

## Overview
This project is a recommendation system implemented using Hierarchical Poisson Factorization (HPF). The system is designed as part of a coursework for the Artificial Intelligence class at the University of Bucharest.

## Project Structure
- **Dataset**: The dataset used in this project is a book recommendation dataset sourced from Kaggle. It contains information about books and the users who have rated them. The project focuses on the ratings provided by users.
- **Model**: The recommendation model is built using Hierarchical Poisson Factorization. The model's implementation includes creating an initial trace of observed data and latent variables, followed by training the model using the Metropolis-Hastings algorithm for 1000 iterations. Further training with an additional 50,000 iterations is also performed for improved accuracy.

## Dataset
The dataset used in this project contains 1,149,780 ratings. Due to the computational cost associated with Markov Chain Monte Carlo (MCMC) methods, the model is initially trained on a subset of the data—specifically, 5 users and 5 items. The selection process involved:
1. Randomly selecting a user and then a book that the user has rated.
2. Subsequent users and books were selected based on the last book chosen, with a preference for users who have read a significant number of books.
3. This process resulted in a 5x5 matrix where ratings are represented, and unrated items are marked with a value of 0.

## Implementation
1. **Model Configuration**:
   - Number of preferences and attributes is set to 3 by default to avoid overloading the model during training.
   
2. **Initial Trace**:
   - An initial trace is created encapsulating the observed data and initial values of the latent variables.

3. **Training**:
   - The model is trained using the Metropolis-Hastings algorithm for 1000 iterations.
   - Mean values for the latent variables are calculated.
   - The model is retrained for an additional 50,000 iterations using the last trace as the initial trace, refining the results.

## References
- **Dataset**: [Kaggle Book Recommendation Dataset](https://www.kaggle.com/datasets/arashnic/bookrecommendation-dataset?resource=download) by MÖBIUS.
- **Model**: Prem Gopalan, David Blei, and Matthias Bettencourt. "Scalable Recommendation with Poisson Factorization."

## How to Run
1. Clone this repository:
    ```bash
    git clone https://github.com/madalin312/probabilistic_recommendation_system
    ```
2. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3. Run the model:
    ```bash
    python train_model.py
    ```

## Author
- **Radu Madalin-Cristian**, Group 407, University of Bucharest.


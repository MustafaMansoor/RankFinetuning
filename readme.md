# Dataset Creation

The project kicked off with the creation of a **unified dataset** by merging two key sources:

- **Amazon Movies and Books Ratings Datasets**: These were combined to form the foundation of the dataset.
- **PAMAP2 Dataset**: This dataset includes physiological data such as **heart rate** and **activity states** (e.g., running, walking). The various activity states were simplified into two categories:
  - **Active**
  - **Relaxed**

Since the Amazon and PAMAP2 datasets did not share common users, **synthetic user IDs** were generated to integrate them into a single dataset tailored for the recommendation task.

# Model Fine-Tuning

For the recommendation system, the **LLaMA 3.2 3B** model was chosen due to its recent release and suitability for the task. A **prompt template** was designed for fine-tuning, structured as follows:

- **Input**:
  - A user’s watched movies, including:
    - **Ratings**
    - **Heart rate**
    - **Activity state** (active or relaxed)
  - A list of books, including:
    - **Heart rate**
    - **Activity state** (active or relaxed)
    - *No ratings provided*
- **Task**:
  - Rank the books based on the user’s likely preferences.

# Evaluation

To evaluate the model’s performance:

- The **predicted book rankings** were compared to the **actual book ratings**.
- The actual ratings were sorted in **decreasing order** to establish the **ground-truth ranking**.
- The **Normalized Discounted Cumulative Gain (NDCG)** metric was used to measure the quality of the predicted rankings.


# Colab Link

```https://colab.research.google.com/drive/1BWaG4F4piLNSSbPKbounJAj0v_FSzqQY?usp=sharing```
# Pokémon Dataset Analysis

## Overview

This project involves analyzing a dataset of Pokémon to uncover trends, insights, and relationships within the data. Python was used for data cleaning, exploration, and answering specific analytical questions.

---

## Key Insights

### 1. Average Weight of Pokémon in Each Generation
- **Question:** What is the average weight of Pokémon in each generation?  
- **Answer:**  
    ```python
    # Group by generation and calculate the average weight
    average_weight_by_gen = df.groupby('generation')['weight'].mean()
    print(average_weight_by_gen)
    ```

---

### 2. Number of Pokémon with Two Types (type1 and type2)
- **Question:** How many Pokémon have two types (type1 and type2)?  
- **Answer:** 526  
- **Method:**
    ```python
    # Count how many Pokémon have a second type (type2)
    num_pokemon_two_types = df['type2'].notna().sum()
    print(num_pokemon_two_types)
    ```

---

### 3. Most Common Primary Type Among All Pokémon
- **Question:** What is the most common primary type (type1) among all Pokémon?  
- **Answer:**  
    ```python
    # Find the most common primary type (type1)
    most_common_type1 = df['type1'].mode()
    print(most_common_type1)
    ```

---

### 4. Statistical Analysis of Pokémon Heights
- **Question:** What is the statistical analysis of Pokémon heights?  
- **Answer:**  
    ```python
    # Get statistical summary of the 'height' column
    height_stats = df['height'].describe()
    print(height_stats)
    ```

---

### 5. Pokémon with the Highest Base Experience (base_exp)
- **Question:** Which Pokémon has the highest base experience (base_exp)?  
- **Answer:**  
    ```python
    # Replace invalid base_exp values and find the Pokémon with the highest base experience
    df['base_exp'] = df['base_exp'].replace('—', 0).astype(float)
    highest_base_exp_pokemon = df.loc[df['base_exp'].idxmax(), 'name']
    print(highest_base_exp_pokemon)
    ```

---

### 6. Average Total Stats for Each Egg Group
- **Question:** What is the average total stats (total) for each egg group?  
- **Answer:**  
    ```python
    # Group by egg group 1 and calculate the average total stats
    average_total_by_egg_group1 = df.groupby('egg_group1')['total'].mean().sort_values().tail(1)
    print(average_total_by_egg_group1)
    ```

---

### 7. Number of Pokémon with a Hidden Ability
- **Question:** How many Pokémon have a hidden ability?  
- **Answer:** 530  
- **Method:**
    ```python
    # Count how many Pokémon have a hidden ability
    num_hidden_ability_pokemon = df['hidden_ability'].count()
    print(num_hidden_ability_pokemon)
    ```

---

### 8. Top 5 Pokémon with the Highest Speed
- **Question:** What are the top 5 Pokémon with the highest speed?  
- **Answer:**  
    ```python
    # Find the top 5 Pokémon with the highest speed
    top_5_speed_pokemon = df['speed'].sort_values().tail(5)
    print(top_5_speed_pokemon)
    ```

---

### 9. Specific Pokémon Names
- **Question:** What are the names of the Pokémon at specific indices?  
- **Answer:**  
    ```python
    # Print names of Pokémon at specific indices
    specific_pokemon_names = [df.loc[i, 'name'] for i in [100, 385, 794, 290, 893]]
    print(specific_pokemon_names)
    ```

---

### 10. Average Attack and Defense Comparison
- **Question:** How does the attack stat compare to the defense stat on average?  
- **Answer:** 5.01 (attack stat is higher on average)  
- **Method:**
    ```python
    # Calculate the average difference between attack and defense stats
    average_attack_defense_diff = (df['attack'] - df['defense']).mean()
    print(average_attack_defense_diff)
    ```

---

### 11. Number of Pokémon in Each Species Category
- **Question:** How many Pokémon are there in each species category?  
- **Answer:**  
    ```python
    # Count the number of Pokémon in each species category
    species_count = df["species"].value_counts()
    print(species_count)
    ```

---

### 12. Average Weight of Pokémon in Each Generation
- **Question:** What is the average weight of Pokémon in each generation?  
- **Answer:**  
    ```python
    # Group by generation and calculate the average weight
    average_weight_by_gen = df.groupby('generation')['weight'].mean()
    print(average_weight_by_gen)
    ```

---

## Technologies Used
- **Programming Language:** Python  
- **Libraries:**
  - `pandas` for data manipulation
  - `numpy` for numerical computations
  - `matplotlib` and `seaborn` for visualization (optional)

---

## How to Run
1. Clone the repository:
   ```bash
   git clone <repository-url>

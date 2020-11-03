# Cats-Adoption-in-Austin

## Business Understanding
Many old cats or cats that are not very popular breed will be euthanized by animal shelters if they cannot be adopted for a long time. Shelters racked their brain for finding adoptive homes for cats. I’m wondering if I am able to contribute a little bit using my data analytics background. 

Fortunately, I found the data covers 29,421 cats from Austin Animal Center from late 2013 to early 2018. The data set collects their breed, color, spay/neuter, age, name, sex, coat as well as their outcomes (eg:Transfer, Adoption, Return to Owner, Died, Euthanasia,Missing, Disposal, Rto-Adopt). Let’s see if we can dive deep into this data and find some interesting insights to figure out what are the factors that affect the chance of adoption. If so, maybe we can help animal shelters to realize how they can increase cat adoption rate.

## Data Understanding
This is a data set for shelter cat outcomes of Austin Animal Center from 10/1/2013 to the present

Important columns in df are:
<b>Breed</b> : Breed of cats (eg: domestic shorthair, domestic mediumhair, domestic longhair, etc.).

<b>Color</b> : Color of cats (eg: orange, black, white, etc.).

<b>Spay/Neuter</b> : If sterilization was done or not.

<b>Outcome_age_(days)</b> : Approximate age of cats upon the outcome days.
  
<b>Cat/Kitten</b> : Whether a cat was of adult or kitten age upon outcome. Kittens are defined as cats of approximately five months old or younger.

<b>Name</b> : Name of cats. Give 'name' a nan if the cat does not have a name.

<b>Outcome_type</b> : The type of outcomes of shelter cats (eg:Transfer, Adoption, Return to Owner, Died, Euthanasia,Missing, Disposal, Rto-Adopt).

<b>Sex_upon_outcome</b> : Intact Male, Intact Female, Spayed Female, Neutered Male

<b>Sex</b> : Male or female.

<b>Cfa_breed</b> : Whether the cat is a rare species. False means regular species and True means rare species.

<b>Coat</b> : Type of coat (eg: apricot, lynx, chocolate, silver, etc.)

## Libraries used in thie project 

1. Pandas - a data analysis and manipulation tool
2. Numpy - a numerical computing tools
3. Matplotlib - a comprehensive library for creating static, animated, and interactive visualizations in Python
4. Seaborn - a Python data visualization library based on matplotlib.
5. Sklearn - a Python machine learning library features various classification, regression and clustering algorithms including support vector machines, random forests, gradient boosting, k-means and DBSCAN, and is designed to interoperate with the Python numerical and scientific libraries NumPy and SciPy.
6. Pylab - a convenience module that bulk imports matplotlib.
7. Pydotplus - a tool provides a Python Interface to Graphviz's Dot language

## Visualized Anlysis

### 1. What happened to the cats in Austin Animal Center？

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/outcome%20distribution.png)

Based on the graph, even though most of the cats had been transferred, there was still a large majority of cats been adopted (Yay!). Cases like euthanasia, return to owner, death, rto-adopt, missing and disposal were actually very rare compared to transfer and adoption. Austin Animal Shelter is really well run! Given the fact that adoption was the most desirable outcome and there are pretty many cases and features to work with, I considered correctly predicting adoption outcome to be a meaningful task.

### 2. Does coat color determine adoption rates?

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/CFA%20%26%20coat%20pattern.png)

The adoption rate of regular species is 42.68%. The adoption rate of rare species is 46.79%. Unexpectedly, whether the cat's breed is expensive or not does not seem to affect their probability of being adopted as people thought.

<a> The most common coat pattern of shelter cats is tabby.
<b> Smoke cats get adopted at the highest rate
<c> The most adopted rare cats are point cats.
  
### 3. What other fun facts?

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Adoption%20rates%20by%20sex%20and%20sterilization.png)

Male cat is more popular in general. Even both female and male cats are spayed or neutered…

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Adoption%20rates%20by%20sex%20and%20name.png)

But, you can easily change everything by just giving female cat a name

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Adoption%20rates%20by%20breed%20and%20coat%20color.png)

You can increase 51% adoption chance for a female cat just by a name! But you can only increase 13.5% chance for male cat by a name

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Adoption%20rates%20by%20age.png)

Age 1~3 years cat is the least popular group. People prefer female cat if it is an old cat.

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Adoption%20rates%20by%20breed%20and%20coat%20color.png)

Appearance of a cat, rather than its breed, seems to be a more important aspect to adopters.

## Modeling:

### 1. Desition Tree

![] (https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Decision%20tree.png)

a. If the cat is not spayed or neuter, and does not have a name, and is not in age range 1~3 years old, it has a very low probability to be adopted.
b. If the cat is spayed or neuter, and it does not have a name, then it would have a higher adoption rate if it is a male cat and a baby kitten.
c. If the cat is spayed or neuter, and it has a name, then it would have a higher adoption rate if it is a baby kitten no matter whether the adoption happened in weekday or weekend.

### 2. Clustering

![](https://github.com/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Pictures/Clustering.png)

We can see that kmeans clustering divided shelter cats into 4 groups mainly by the differences in their ages. Cluster 0 is consisted of 3 years old cats which has the lowest adoption rate. On the other hand, cluster 1 is the "kitten cluster" which has the highest 46% adoption rate. The other two groups all belong to the "old cat" group. Compared with cluster 2, cluster 3 has a slightly higher male cats percentages which brings a higher adoption rate. Lastly, both cluser 2 and 3 have a higher percentages in names and famous cats. But those features still cannot change the impact of age in terms of the chance of adoption.

### 3. Regression

                           Logit Regression Results                           
==============================================================================
Dep. Variable:               adoption   No. Observations:                25792
Model:                          Logit   Df Residuals:                    25784
Method:                           MLE   Df Model:                            7
Date:                Tue, 20 Mar 2018   Pseudo R-squ.:                  0.3477
Time:                        12:38:35   Log-Likelihood:                -11493.
converged:                       True   LL-Null:                       -17619.
                                        LLR p-value:                     0.000
====================================================================================
                       coef    std err          z      P>|z|      [0.025      0.975]
------------------------------------------------------------------------------------
name                 2.0220      0.036     56.235      0.000       1.952       2.093
outcome_age_days    -0.0006   1.83e-05    -34.470      0.000      -0.001      -0.001
cfa_breed            0.2158      0.073      2.955      0.003       0.073       0.359
male                 0.3657      0.033     10.983      0.000       0.300       0.431
sterilization        2.7705      0.048     58.118      0.000       2.677       2.864
weekend              0.9212      0.035     26.017      0.000       0.852       0.991
common_coat         -0.1935      0.055     -3.494      0.000      -0.302      -0.085
intercept           -3.6671      0.072    -50.646      0.000      -3.809      -3.525
====================================================================================

a. If a cat has a name, the probability of adoption increases by around 655% holding other variables constant.
b. If a cat's age increase by one day, the probability of adoption decreases by around 0.06% holding other variables constant.
c. If a cat has cfa certificate (rare species), the probability of adoption increases by around 24% holding other variables constant.
d. If a cat is spayed or neuter, the probability of adoption increases by around 1497% holding other variables constant.
e. If a cat is a male, the probability of adoption increase by around 44% holding other variables constant.
f. If a cat has a common coat color, the probability of adoption decreases by around 18% holding other variables constant.
g. The probability of adoption is much higher if it is in weekend.

The adoption rate is mainly influenced by name, sterilization and kitten.

## Conclusion:
I sliced and diced the data from multiple dimensions and now I have some recommendations to shelters and people who are looking for a cat:
Please give every cat in shelter a name! Currently, only 56% of cats in shelter have a name. By giving shelter cats a name can increase adoption rate by 44 percentage point, especially for female cats, the influence is more than 51 percentage point.
If funding allows, make sure to neuter or spay cats can increase adoption rate by 50%. Currently, only 68.4% of cats in shelter accepted sterilization.
Next time when you visit an animal shelter, please pick those who are female cats without a name, 1~3 years old cats, female kittens, old male cats, domestic-breed cats, black/orange/white cats. They are more in need of help.
Finally, don’t forget no matter what cat you have chosen, please treat them with all your love, because they are probably only a part of your world, but you are indeed the whole world of them.

## Python Jupyter Notebook in nbviewer
https://nbviewer.jupyter.org/github/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Cats%20Adoption%20in%20Austin.ipynb

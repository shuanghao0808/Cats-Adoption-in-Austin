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


## Conclusion:
I sliced and diced the data from multiple dimensions and now I have some recommendations to shelters and people who are looking for a cat:
Please give every cat in shelter a name! Currently, only 56% of cats in shelter have a name. By giving shelter cats a name can increase adoption rate by 44 percentage point, especially for female cats, the influence is more than 51 percentage point.
If funding allows, make sure to neuter or spay cats can increase adoption rate by 50%. Currently, only 68.4% of cats in shelter accepted sterilization.
Next time when you visit an animal shelter, please pick those who are female cats without a name, 1~3 years old cats, female kittens, old male cats, domestic-breed cats, black/orange/white cats. They are more in need of help.
Finally, don’t forget no matter what cat you have chosen, please treat them with all your love, because they are probably only a part of your world, but you are indeed the whole world of them.

## Python Jupyter Notebook in nbviewer
https://nbviewer.jupyter.org/github/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Cats%20Adoption%20in%20Austin.ipynb

# Cats-Adoption-in-Austin

## Summary
Many old cats or cats that are not very popular breed will be euthanized by animal shelters if they cannot be adopted for a long time. Shelters racked their brain for finding adoptive homes for cats. I’m wondering if I am able to contribute a little bit using my data analytics background. 

Fortunately, I found the data covers 29,421 cats from Austin Animal Center from late 2013 to early 2018. The data set collects their breed, color, spay/neuter, age, name, sex, coat as well as their outcomes (eg:Transfer, Adoption, Return to Owner, Died, Euthanasia,Missing, Disposal, Rto-Adopt). Let’s see if we can dive deep into this data and find some interesting insights to figure out what are the factors that affect the chance of adoption. If so, maybe we can help animal shelters to realize how they can increase cat adoption rate.

## Data Description
This is a data set for shelter cat outcomes of Austin Animal Center from 10/1/2013 to the present

Important columns in df are:
<b>Breed</b> : Breed of cats (eg: domestic shorthair, domestic mediumhair, domestic longhair, etc.).
<b>Color</b> : Color of cats (eg: orange, black, white, etc.).
<b>Spay/Neuter</b> : If sterilization was done or not.
<b>Outcome_age_(days) : Approximate age of cats upon the outcome days.
<b>Cat/Kitten</b> : Whether a cat was of adult or kitten age upon outcome. Kittens are defined as cats of approximately five months old or younger.
<b>Name</b> : Name of cats. Give 'name' a nan if the cat does not have a name.
<b>Outcome_type</b> : The type of outcomes of shelter cats (eg:Transfer, Adoption, Return to Owner, Died, Euthanasia,Missing, Disposal, Rto-Adopt).
<b>Sex_upon_outcome</b> : Intact Male, Intact Female, Spayed Female, Neutered Male
<b>Sex</b> : Male or female.
<b>Cfa_breed</b> : Whether the cat is a rare species. False means regular species and True means rare species.
<b>Coat</b> : Type of coat (eg: apricot, lynx, chocolate, silver, etc.)

## Conclusion:
I sliced and diced the data from multiple dimensions and now I have some recommendations to shelters and people who are looking for a cat:
Please give every cat in shelter a name! Currently, only 56% of cats in shelter have a name. By giving shelter cats a name can increase adoption rate by 44 percentage point, especially for female cats, the influence is more than 51 percentage point.
If funding allows, make sure to neuter or spay cats can increase adoption rate by 50%. Currently, only 68.4% of cats in shelter accepted sterilization.
Next time when you visit an animal shelter, please pick those who are female cats without a name, 1~3 years old cats, female kittens, old male cats, domestic-breed cats, black/orange/white cats. They are more in need of help.
Finally, don’t forget no matter what cat you have chosen, please treat them with all your love, because they are probably only a part of your world, but you are indeed the whole world of them.

## Python Jupyter Notebook in nbviewer
https://nbviewer.jupyter.org/github/shuanghao0808/Cats-Adoption-in-Austin/blob/master/Cats%20Adoption%20in%20Austin.ipynb

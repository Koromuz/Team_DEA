**Question:** Is the dataset imbalanced? Which class matters most for a dropout early-warning system, and why?

>Looking at the dataset, we can see it is imbalanced: students marked as "graduate" outnumber those categorized as "dropout" and "enrolled" by a factor of two and three, respectively. Moreover, for a system that alerts authorities to a possible dropout, the most important class would be the dropout category; the reasoning is that if a student is actually at risk of dropping out and the system fails to acknowledge this, this could be classified as a failure of the system itself; if the system misclassifies a student who is not at risk, it is easier to reclassify them to their correct category.



## Task 6: Interpret (15 min)
Write these three sentences in **REPORT.md** (draft them here first):
1. Which model would you trust for an early-warning system?
    > We would trust the random forest for an early warning system. The reasoning for the answer is that random forest had the best validation micro F1 and also led in 5-fold cross validation.

2. Which class does it struggle with? (Use per-class recall and the confusion matrix.)
    > It struggles most with the enrolled class, where 70 out of 159 enrolled students were labeled as dropouts or graduate, and it also misses 84 out of 284 actual dropouts.

3. One deployment risk.
    > A deployment risk of the model is that it takes in background features such as nationality and parents' qualification and occupation, so students could possiblely be flagged for who they are rather than how they are perfoming academically, stigmatizing the students and wasting valuable resources in sending the support actual students who are at risk need.



## Reflection questions
1. Where could a model like this help in your community, and who would be harmed by its errors?

   > The first thing we thought of would be in healthcare where this model can assist in accurate medical diagnosis by analazing exisitng patient data which could lead to better treatment outcomes. However patients with diseases that have less data may be misdiagnose and could be given the wrong treatment.

2. What non-public data would you need, and how would you get permission?

   > We would need non-public data such as patient symptoms, demographic information, medical history, and diagnostic outcomes to name a few in order to train this model in healthcare. To get this data we would coordinate with the appropriate authorities and create letter to get consent from patients and doctors to use the data only for educational purposes and for the communities benefit.

3. If recall for one class were much lower for one group of students, what would you do before deploying?

   > Before deploying, we would investigate why that particular group had much lower recall. Would check the dataset for imbalances, missing information, or possible biases that could affect the results. Should also test and adjust the model to improve its performance for that group. We would only consider deploying it once the model provides more consistent and fair results across all groups.

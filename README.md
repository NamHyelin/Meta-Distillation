# Meta-Distillation
Split one model and distillation from the end to the hidden layer,
and refer the former layers as student, and the later layers as teacher.

To distillation knowledge before the smashed data flows through the whole layer(;teacher),
teacher gives his meta logit to student related to the batch

![image](https://user-images.githubusercontent.com/74347397/146889004-81f359a6-970d-408d-8c94-e703ac2db25f.png)

# Reconstruction loss
When training student with its local loss with distillation loss, (local parallel training)
The hidden layer (student's out layer) will contain lots of information of class,
and the entire model gets to wrong optimal point, wrong bias.
To avoid this, we add reconstruction loss to student, to increase the mutual information btw x and z I(X;Z)
(Yulin Wang, Zanlin Ni, Shiji Song, Le Yang & Gao Huang, REVISITING LOCALLY SUPERVISED LEARNING:AN ALTERNATIVE TO END-TO-END TRAINING, ICLR 2021)
![image](https://user-images.githubusercontent.com/74347397/146889547-46cf3d43-e4e6-4682-8c8f-3f6d6120b7b2.png)

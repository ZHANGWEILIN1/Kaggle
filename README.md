# ACSE 4.4 - Machine Learning Miniproject

## User Guidance

1. Please check [workflow.pdf](workflow.pdf) for marking workflow

2. Please check [WideResNet_Algorithm.pdf](WideResNet_Algorithm.pdf) for marking algorithm

3. There are two other `.pdf` files [Best-vs-Worst_classification_implication.pdf](Best-vs-Worst_classification_implication.pdf) and [Investigate_input_for_data_augmentation.pdf](Investigate_input_for_data_augmentation.pdf), which evaluate the strategy we used

4. The [GreyImage_Ratio_Analysis.ipynb](GreyImage_Ratio_Analysis.ipynb) generated analysis on grey images

5. Please check [ELBO_PRE_SLIDES.pptx](ELBO_PRE_SLIDES.pptx) for presentation slides

## Results 

1. The first final model generation code is [WRN_101-2_3epoch.ipynb](WRN_101-2_3epoch.ipynb). The model weights for our res101 model is stored on [Google Drive](https://drive.google.com/open?id=1N-n8sVKWSevo2taUVuK7wa05F9U1xa6B)

2. The second final model generation code is [WRN_101-2_4epoch.ipynb](WRN_101-2_4epoch.ipynb). The model weights for our res101 model is stored on [Google Drive](https://drive.google.com/open?id=1iDel2F2YfO_TUhqP-BxLrngGinRt4zoT)

### Resuming training

When training the above neural network for 3 epochs, saving the model, 
and then later loading the model to train for an additional epoch, the resulting model has slightly
different weights than training the neural network for 4 epochs in one go (the accuracy on the training
models were 0.987 and 0.985 respectively)

Despite the random seeds provided being idential in both cases, the slight variation is caused by 
the random shuffle occuring in each epoch, which alters the training model; in the first case when
we resume our model, the shuffled order of the training set for the 4th epoch is idential to the 
1st. On the model trained without saving/resuming, the shuffled order for the 4th epoch is different

Given we're training so few epochs, the latter case *without* resuming would be superior since having
1st and 4th epoch shuffle order be idential partly defeat the purpose of shuffling the training order,
which is to reduce overfitting the training set

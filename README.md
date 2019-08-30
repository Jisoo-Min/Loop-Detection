# Loop-Detection
For a long time, many people want to generate code from sentences automatically. Thanks to machine learning and deep learning, we can try to deal with this problem. As part of efforts to automatically generate code, we predict whether loop will be used in the code when a sentence is given.
To find loop, we use Neural Network ,Goggle Sentence Encoder ,whole sentences(Codingbat.com)
For example, given sentence such as “Given an array of int, return the sum of all the elements.”, 

```java
public int answer(int arr[])
{
  int num = 0;
  for(int i =0; i<arr.length(); i++)
  {
      sum = sum +arr[i];
  }
  return sum;
}
```


# Requirements
To run our code, you need those libraries installed
 
 * tensorflow
 * tensorflow_hub
 * pandas
 * numpy
 * sklearn.model_selection
 * matplotlib.pyplot
 * keras
 * https://tfhub.dev/google/universal-sentence-encoder/1
 
 
 
# Dataset
Prepare labeled dataset as an input to train Neural Network(NN) model. 
Your Dataset should meet the following conditions.

 1. Dataset is a csv file, which is a list of vector values.
 2. Label is 1 or 0. If label is 1 that mean is sentence have loop, otherwise 0 is         sentence don't have loop.
 
You can see the example() of our input_file.

 1. we labeled 317 sentences 
 
# How to execute code

Our NN code is [here](https://github.com/jiisoo/NLP-FindLoop/blob/master/loop-detection/NN_with_google_sentence_encoder.ipynb)

## [NN_with_google_sentence_encoder.ipynb](https://github.com/jiisoo/NLP-FindLoop/blob/master/loop-detection/NN_with_google_sentence_encoder.ipynb)

  1. Data processing<br/>
   We have Codingbat dataset we made. It has sentences and vector values and label.               For making vector values we use Google Sentence Encoder. Google Sentence Encoder change vector values from sentences. 
   
     Sentence = Given an array of ints length 3, return the sum of all the elements.<br/><br/>
     Vector values = [[ 0.00020983 -0.01434974 -0.0620535  ...  0.01654282 -0.06327306
     -0.02807822]
     [-0.01388634 -0.00700146 -0.02114584 ... -0.01939107 -0.06096156
     -0.02967445]
     [-0.01593745 -0.04505406 -0.04514664 ... -0.01364841 -0.05955384
     -0.02636058]]
   
   
  2. Model generation<br/>
     With several settings, instanciate the model. For example, it takes the number of hidden layers, context-size, dimension of word embedding, etc. We use dense model that is basic and normal model of NN
   
  3. Training<br/>
     The training operate according to the epochs and the number of training data. For  each epoch, the best f1-score is recorded.
     
  4. Evaluation<br/> 
     During training, the best f1-score is recorded. At the end of the training, the best f1-score is calculated in testset.




  
  

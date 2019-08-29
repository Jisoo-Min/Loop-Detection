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

 1. Dataset is a csv file, which is a list of vector values
 2. Label is 1 or 0 repres in other words, label should start with 'I', 'B' or just 'O'.

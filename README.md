# Speech Emotion Recognition

![emotion](https://user-images.githubusercontent.com/67755812/204617857-914de4c1-c303-4d7a-98ea-518987cae2a5.gif)



<b> Dataset Link: https://www.kaggle.com/code/hrugvedkolhe/speech-emotion/data </b>

In the project, I have build a Deep Learning model that is trained on emotion dataset or better yet speech emotion classification through audio data. We have an extract_feature function which is using some other functions to extract different information from the audio file. We use the MLPClassifier which stands for Multi-Layer Perceptron classifier. 

MLP which in the name itself connects to a Neural Network. Unlike other classification algorithms such as support Vectors or Naive Bayes Classifer relies on an underlying Neural Network to perform the task of classification.

I have used Librosa as it is used for music and audio analysis and also to wordk with audio data like music genrations or be able to make speech recognitions. It provides a lot of building blocks necessary to create the music information, which later can be processed. Well also, having another purpose in life, like categorzing ehat type of emotion it is protrayed through thr audio when someone might want to find out which the sound is in the sing file. So all of these can be processed through information that can be extracted through functions created inside Librosa package. 
Soundfile is used to reading and writing support some types like wav, mp3, etc.

So I have a created a function "extract_feature" to extract feature or information from the audio file, which can be used as input to the model so that we can train that on the data that I get from the function. So we have a chroma (audio chroma) which 	pertains to 12 different pitch classes defined for an audio. Due to chroma what happens is that, if the audio has pitch or certain class, it would say that this speech is present in the audio files. It would send back something like zeros and ones, it would tell that what pitch classes ae present for this particular audio file. The main property for chroma feature is that they capture harmonic and melodic charactristics of music by being robust to changes in the instrumentation used in the particular audio file. Next, is mfcc it is called as Mel-frequency cepstral coefficients which represents the short term power spectrum of a sound. So basically we are using mfcc to get the information about the vocal track from the audio file. https://www.analyticsvidhya.com/blog/2021/06/mfcc-technique-for-speech-recognition/ for detailed information.
And then we mel-spectogram frequency, it has a list of frequencies which are regarded in mel's spectogram.  https://medium.com/analytics-vidhya/understanding-the-mel-spectrogram-fca2afa2ce53

Then we will laod the data with the extracted features and we are returning the training and testing dataset.
So we have 180 features that we have extracted from "extract_feature" function.

So I have created a two MLPClassifier models:
### First Model : 

![mlp_model](https://user-images.githubusercontent.com/67755812/203573516-94556cb7-cdcd-4c32-97ce-c5e1dd8ab18e.PNG)

As we can see the batch_size =256, and hidden_layer_sizes=(300,) and epsilon=1e-08. As it has only one hidden layer the score of the model is 94.9% and accuracy is 72.92%. The loss value also decreases after 175, it would decrease more and get constant.

![model](https://user-images.githubusercontent.com/67755812/203573672-274cc9e8-77a1-4141-a4f4-6e722b22ab2b.png)



### Second Model:

![mlp_model](https://user-images.githubusercontent.com/67755812/203573708-85dbc01e-e6dc-41d3-b0ae-37699b6740b7.PNG)


In second model we can see that I have decreased a batch_size and added 4 layers to hidden_layer_size, iteration, learning_rate and alpha are same. After training the model the score is 89.2% and accuracy is 74.48%.
In the plot we can see that after 120 the loss is decreasing. This model is giving better results than our first model.

![model1](https://user-images.githubusercontent.com/67755812/203573877-162a3196-bbbb-4d84-b4b4-9931105c3a09.png)



### Conclusion
#### So the second model is performing better we will be saving the second model.

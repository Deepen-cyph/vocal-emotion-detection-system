# vocal-emotion-detection-system
## Introduction

This project aims to develop a machine learning model capable of detecting emotions from speech, addressing the growing demand for personalized experiences. By analyzing vocal inputs, our emotional speech recognition system can identify the speaker's emotions, enabling tailored recommendations and responses.

## Applications

Marketing: Emotion-based product recommendations.
Automotive: Adjusting autonomous vehicle behavior based on driver emotions.
Healthcare: Monitoring patient emotions for better mental health support.
Customer Service: Enhancing interactions by adapting to customer emotions.
Entertainment: Personalized content and adaptive gaming experiences.

## Dataset

### RAVDESS:

Contains approximately 1,500 audio files from 24 actors (12 male, 12 female).
Each actor records short audios in 8 different emotions: neutral, calm, happy, sad, angry, fearful, disgust, and surprised.
The 7th character in each audio file's name indicates the emotion.

### SAVEE:

Comprises around 500 audio files recorded by 4 different male actors.
The first two characters of the file name correspond to the different emotions portrayed.

## Audio files:
Tested out the audio files by plotting out the waveform and a spectrogram to see the sample audio files.
Waveform
![image](https://github.com/user-attachments/assets/5ed89121-9965-4811-8e8d-1f52cc5b651f)

*Spectrogram*
![image](https://github.com/user-attachments/assets/34d812cb-e59f-469d-8df2-036426548c1f)

## Feature Extraction
The next step involves extracting features from the audio files to help our model differentiate between them. For this, we use the LibROSA library in Python, which is widely used for audio analysis.

![image](https://github.com/user-attachments/assets/d38e27eb-97c8-4de4-842d-aaf31ce2db79)

Key Points:
Timing: All audio files are trimmed or padded to a length of 3 seconds to ensure a consistent number of features.
Sampling Rate: The sampling rate of each file is doubled, maintaining the sampling frequency constant. This increases the number of features, aiding in classification, especially when the dataset is small.
The extracted features include various audio characteristics such as:

Mel-frequency cepstral coefficients (MFCC)
Chroma feature
Spectral contrast
Tonnetz

![image](https://github.com/user-attachments/assets/0e7156f1-e108-4cd9-b48d-2a6c3d09db69)

# Model Selection and Performance

Since the project is a classification problem, a Convolutional Neural Network (CNN) was the obvious choice. We also built Multilayer Perceptrons (MLP) and Long Short Term Memory (LSTM) models, but they underperformed with very low accuracies and couldn't reliably predict the right emotions.

Building and tuning a model is a time-consuming process. The idea is to start small without adding too many layers just for complexity's sake. After experimenting with different layer configurations, the CNN model that provided the highest validation accuracy achieved a bit more than 70% on test data.

![image](https://github.com/user-attachments/assets/0caf9b70-1bfb-4240-8c74-68873ee32d1b)

#Prediction

![image](https://github.com/user-attachments/assets/9e31722b-b17e-4584-ab0b-c47237aebb07)

# Testing out with live voices.

To further evaluate the model, we tested it with live voice inputs. This involved real-time emotion detection from live speech, providing insights into the model's performance in practical, real-world scenarios. The results demonstrated the model's potential for real-time applications, though there is room for improvement to enhance accuracy and robustness.

![image](https://github.com/user-attachments/assets/0cfc636e-3307-4ae3-91d1-8b05ef5b2d5e)
![image](https://github.com/user-attachments/assets/c0606dd1-51f3-49e0-afab-27b15dbb29bc)

# Conclusion

This project demonstrates the potential of using machine learning to detect emotions from speech. By leveraging Convolutional Neural Networks (CNNs), we achieved a validation accuracy of over 70% on test data. While Multilayer Perceptrons (MLPs) and Long Short Term Memory (LSTM) models were explored, they did not perform as well as the CNN model.

The process of building and tuning the model was extensive, and starting with a simpler architecture proved beneficial. Testing with live voice inputs further validated the model's applicability in real-world scenarios, although there is still room for improvement.

Moving forward, refining the model and expanding the dataset can help enhance the accuracy and robustness of the emotional speech recognition system. This technology holds promise for various applications, from personalized marketing and automotive safety to improved customer service and healthcare support.











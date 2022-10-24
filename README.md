# quel-accent
Accent Detection on skewed audio dataset with oversampling and audio augmentation

## Problem Statement 🤔
Given an audio clip of a person speaking in English, identify the native language of the speaker.

## Approach 🚀
We noticed that the data was heavily skewed.  

For example, the number of audio samples for English and Spanish were much larger than others. Some like Nepali had very few (barely 10). To minimize bias during training, we went for oversampling and audio augmentation. We've also considered the top 30 languages, because the rest of them have lesser than 10 audio files.

Oversampling is done by splitting the audio into frames. Then, until we reach 100 datapoints for each language, we do augmentation. We pick a random audio sample, and add some variation to it by introducing a time shift or Gaussian Noise.  

Then, each audio frame (which stores the time series data of the audio) is converted to its respective Mel-Spectrogram, which is essentially an image that can act as feature and can be passed on to a CNN.

Note: the original dataset had audio files in mp3 format. We've converted them to wav to make processing faster (and library usage easier). 

---

## How this started
This project was made during IIITH's Megathon (2022), Qualcomm track. [Placed 1st]

Made with ❤️ by [Md Faizal Karim](https://github.com/FaizalKarim280280), [Aryaman Kolhe](https://github.com/Chasmiccoder), [Ishan Kavathekar](https://github.com/ishank31), [Kunal Bhosikar](https://github.com/KUNAL-KAMALKISHOR-BHOSIKAR), [Prakhar Jain](https://github.com/prakharjain3)

# StyleTTS-VC

One-shot voice conversion (VC) aims to convert speech from any source speaker to an arbitrary target speaker with only one reference speech audio from the target speaker, which relies heavily on disentangling the speaker identity and speech content, a task that still remains challenging. Here, we propose a novel approach to learning disentangled speech representation by transfer learning from style-based text-to-speech (TTS) models. The style-based TTS models are able to adapt to new unseen speakers during training, and with cycle consistent and adversarial training, the model can perform transcription-guided any-to-any voice conversion with a high degree of naturalness and similarity. By learning an additional mel-spectrogram encoder through a teacher-student knowledge transfer scheme, our approach results in completely disentangled speech representation without needing the input text. The subjective evaluation shows that our approach can significantly outperform the previous state-of-the-art one-shot voice conversion models in both naturalness and similarity. In addition, since our architecture is entirely convolutional, it can perform real-time inference with a faster-than-real-time vocoder.

---

## Any-to-any Conversion

All of the following audios are converted from **an unseen speaker** to **another unseen speaker** during training. For a fair comparison to the baseline models, all audios are downsampled to 16k Hz.

**All utterances are completely unseen during training, and the results are uncurated (NOT cherry-picked) unless otherwise specified**.

For more audio samples, please go to our survey used for MOS evaluation [here](https://survey.alchemer.com/s3/6794885/VC40-B1).  You may have to randomly select some answers before proceeding to the next page.

**Sample 1 and 2**

|              | Sample 1 (p252 → p268) | Sample 2 (p256 → p278) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p268.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p278.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p268.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p278.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p268.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p278.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p268.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p278.wav"></source> </audio>     |
| **StyleTTS-VC** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p268.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p278.wav"></source> </audio>      |

**Sample 3 and 4 **

|              | Sample 3 (p267 → p256) | Sample 4 (p273 → p287) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p256.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p287.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p256.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p287.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p256.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p287.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p256.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p287.wav"></source> </audio>     |
| **StyleTTS-VC** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p256.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p287.wav"></source> </audio>      |

---

## Ablation Study

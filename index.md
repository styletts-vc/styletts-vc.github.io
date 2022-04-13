# StyleTTS-VC

One-shot voice conversion (VC) aims to convert speech from any source speaker to an arbitrary target speaker with only one reference speech audio from the target speaker, which relies heavily on disentangling the speaker identity and speech content, a task that still remains challenging. Here, we propose a novel approach to learning disentangled speech representation by transfer learning from style-based text-to-speech (TTS) models. The style-based TTS models are able to adapt to new unseen speakers during training, and with cycle consistent and adversarial training, the model can perform transcription-guided any-to-any voice conversion with a high degree of naturalness and similarity. By learning an additional mel-spectrogram encoder through a teacher-student knowledge transfer scheme, our approach results in completely disentangled speech representation without needing the input text. The subjective evaluation shows that our approach can significantly outperform the previous state-of-the-art one-shot voice conversion models in both naturalness and similarity. In addition, since our architecture is entirely convolutional, it can perform real-time inference with a faster-than-real-time vocoder.

---

## Any-to-Any Conversion

All of the following audios are converted from **an unseen speaker** to **another unseen speaker** during training. For a fair comparison to the baseline models, all audios are downsampled to 16k Hz. The input to AGAIN-VC	and StyleTTS-VC was trimmed so the output has a different length from the input. 

**All utterances are completely unseen during training, and the results are uncurated (NOT cherry-picked) unless otherwise specified**.

For more audio samples, please go to our survey used for MOS evaluation [here](https://survey.alchemer.com/s3/6794885/VC40-B1).  You may have to randomly select some answers before proceeding to the next page.

**Sample 1 and 2**

|              | Sample 1 (p267 → p287) | Sample 2 (p287 → p256) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p287.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p256.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p287.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p256.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p287.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p256.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p287.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p256.wav"></source> </audio>     |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p287.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p256.wav"></source> </audio>      |

**Sample 3 and 4**

|              | Sample 3 (p252 → p278) | Sample 4 (p256 → p268) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p278.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p268.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p278.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p268.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p278.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p268.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p278.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p268.wav"></source> </audio>     |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p278.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p268.wav"></source> </audio>      |

**Sample 5 and 6**

|              | Sample 5 (p273 → p232) | Sample 6 (p300 → p339) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p232.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/p339.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p232.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/p339.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p232.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/p339.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p232.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/p339.wav"></source> </audio>     |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p232.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/p339.wav"></source> </audio>      |

---

## Ablation Study

We present four samples of ablation study for conditions described in Table 2 in our paper on VCTK dataset. 

**Sample 1 and 2**

|              | Sample 1 | Sample 2 |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/10.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/32.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/10.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/32.wav"></source> </audio> |
|    **Baseline**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/10.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/32.wav"></source> </audio>     |
|    **No ASR Loss**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/10.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/32.wav"></source> </audio>     |
| **No Cycle Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/10.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/32.wav"></source> </audio>      |
| **With Latent Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/10.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/32.wav"></source> </audio>      |

**Sample 3 and 4**

|              | Sample 3 | Sample 4 |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/33.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/37.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/33.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/37.wav"></source> </audio> |
|    **Baseline**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/33.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/37.wav"></source> </audio>     |
|    **No ASR Loss**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/33.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/37.wav"></source> </audio>     |
| **No Cycle Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/33.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/37.wav"></source> </audio>      |
| **With Latent Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/33.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/37.wav"></source> </audio>      |


# StyleTTS-VC

One-shot voice conversion (VC) aims to convert speech from any source speaker to an arbitrary target speaker with only one reference speech audio from the target speaker, which relies heavily on disentangling the speaker's identity and speech content, a task that still remains challenging. Here, we propose a novel approach to learning disentangled speech representation by transfer learning from style-based text-to-speech (TTS) models. With cycle consistent and adversarial training, the style-based TTS models can perform transcription-guided one-shot VC with high fidelity and similarity. By learning an additional mel-spectrogram encoder through a teacher-student knowledge transfer and novel data augmentation scheme, our approach results in disentangled speech representation without needing the input text. The subjective evaluation shows that our approach can significantly outperform the previous state-of-the-art one-shot voice conversion models in both naturalness and similarity. 

---

## Any-to-Any Conversion

All of the following audios are converted from **an unseen speaker** to **another unseen speaker** during training. For a fair comparison to the baseline models, all audios are downsampled to 16k Hz. The input to VC models was trimmed so the output has a different length from the input. 

**All utterances are completely unseen during training, and the results are uncurated (NOT cherry-picked) unless otherwise specified**.

For more audio samples, please go to our survey used for MOS evaluation [here](https://survey.alchemer.com/s3/6794885/VC40-B1).  You may have to randomly select some answers before proceeding to the next page.

**Sample 1 and 2**

|              | Sample 1 (p294 → p326) | Sample 2 (p261 → p225) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/55.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/76.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/55.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/76.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/55.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/76.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/55.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/76.wav"></source> </audio>     |
| **YourTTS** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/55.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/76.wav"></source> </audio>      |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/55.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/76.wav"></source> </audio>      |

**Sample 3 and 4**

|              | Sample 3 (p225 → p245) | Sample 4 (p261 → p234) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/46.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/15.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/46.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/15.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/46.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/15.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/46.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/15.wav"></source> </audio>     |
| **YourTTS** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/46.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/15.wav"></source> </audio>      |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/46.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/15.wav"></source> </audio>      |

**Sample 5 and 6**

|              | Sample 5 (p238 → p347) | Sample 6 (p302 → p238) |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/16.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/source/19.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/16.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/gt/19.wav"></source> </audio> |
|    **AGAIN-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/16.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/againvc/19.wav"></source> </audio>     |
|    **VQMIVC-VC**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/16.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/vqmivc/19.wav"></source> </audio>     |
| **YourTTS** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/16.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/yourtts/19.wav"></source> </audio>      |
| **StyleTTS-VC (Proposed)** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/16.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/demo/stylettsvc/19.wav"></source> </audio>      |

---

## Ablation Study

We present four samples of ablation study for conditions described in Table 2 in our paper on VCTK dataset. 

**Sample 1 and 2**

|              | Sample 1 | Sample 2 |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/10.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/32.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/10.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/32.wav"></source> </audio> |
|    **Baseline**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/10.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/32.wav"></source> </audio>     |
|    **No Augmentation**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noaug/10.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noaug/32.wav"></source> </audio>     |
|    **No MI Loss**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/10.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/32.wav"></source> </audio>     |
| **No Cycle Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/10.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/32.wav"></source> </audio>      |
| **With Latent Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/10.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/32.wav"></source> </audio>      |

**Sample 3 and 4**

|              | Sample 3 | Sample 4 |
|:------------:|:-------:|:-------:|
|    **Source**    |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/33.wav"></source> </audio>   |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/source/37.wav"></source> </audio>  |
|    **Target**    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/33.wav"></source> </audio>   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/gt/37.wav"></source> </audio> |
|    **Baseline**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/33.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/baseline/37.wav"></source> </audio>     |
|    **No Augmentation**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noaug/33.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noaug/37.wav"></source> </audio>     |
|    **No MI Loss**   |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/33.wav"></source> </audio>    |     <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/noasr/37.wav"></source> </audio>     |
| **No Cycle Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/33.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/nocycle/37.wav"></source> </audio>      |
| **With Latent Loss** |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/33.wav"></source> </audio>     |    <audio controls="controls">  <source type="audio/wav" src="https://raw.githubusercontent.com/styletts-vc/styletts-vc.github.io/main/ablation/latent/37.wav"></source> </audio>      |


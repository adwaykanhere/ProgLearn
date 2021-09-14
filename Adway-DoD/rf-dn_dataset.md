# Summary of datasets that can be used for audio based tasks.



## 1. FSD50K dataset

Eduardo Fonseca, Xavier Favory, Jordi Pons, Frederic Font, Xavier Serra. "FSD50K: an Open Dataset of Human-Labeled Sound Events", arXiv:2010.00475, 2020.

- 51,197 sounds unequally distributed in 200 classes drawn from the [Audioset Ontology](https://research.google.com/audioset////////ontology/index.html)
- Total time: 108.3 hours of multi-labeled audio files
- Sounds from physical sound sources and production mechanisms, including human sounds, sounds of things, animals, natural sounds, musical instruments and more.
- Clips are of variable length from 0.3 to 30s
- All clips are provided as uncompressed PCM 16 bit 44.1 kHz mono audio files.

Data set is split in to Dev and Eval sets.

### Dev set

- Dev set contains 40,966 audio clips totalling 80.4 hours of audio.
- Avg duration/clip: 7.1s
- Labels can be incomplete

### Eval set

- 10,231 audio clips totalling 27.9 hours of audio
- Avg duration/clip: 9.8s

## Structure of dataset

Each row in the audio csv file from Dev set contains:

- fname: the file name without the .wav extension, e.g., the fname 64760 corresponds to the file 64760.wav in disk. This number is the Freesound id.
- labels: the ground truth
- mids: the Freebase identifiers corresponding to the class labels, as defined in the AudioSet Ontology specification
- split: whether the clip belongs to train or val

The eval set has the same structure but without the split parameter. 


## 2. The LJ Speech Dataset

@misc{ljspeech17,

  author       = {Keith Ito and Linda Johnson},

  title        = {The LJ Speech Dataset},

  howpublished = {\url{https://keithito.com/LJ-Speech-Dataset/}},

  year         = 2017}

- Open dataset with 13,100 short audio cips of a single speaker reading 7 books.
- Each clip is transcribed
- Clips vary from 1-10 secs
- Total time: approx 24 hrs.
- File format: One record per line delimited by a pipe character
- Fields: 
    - ID: this is the name of the corresponding .wav file
    - Transcription: words spoken by the reader (UTF-8)
    - Normalized Transcription: transcription with numbers, ordinals, and monetary units expanded into full words (UTF-8).
- Each audio file is a single-channel 16-bit PCM WAV with a sample rate of 22050 Hz
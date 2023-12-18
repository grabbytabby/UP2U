# UP2U
Getcha Barz Up
import librosa
import numpy as np
from IPython.display import Audio

# Load drum samples
kick, sr_kick = librosa.load('kick_sample.wav', sr=None)  # Replace with your kick sample file path
snare, sr_snare = librosa.load('snare_sample.wav', sr=None)  # Replace with your snare sample file path
hihat, sr_hihat = librosa.load('hihat_sample.wav', sr=None)  # Replace with your hi-hat sample file path

# Adjust the length of the samples to be the same
min_length = min(len(kick), len(snare), len(hihat))
kick = kick[:min_length]
snare = snare[:min_length]
hihat = hihat[:min_length]

# Combine the samples to create a hip-hop beat
beat = 0.7 * kick + 0.5 * snare + 0.3 * hihat

# Normalize the beat
beat = librosa.util.normalize(beat)

# Play the beat
Audio(data=beat, rate=sr_kick)

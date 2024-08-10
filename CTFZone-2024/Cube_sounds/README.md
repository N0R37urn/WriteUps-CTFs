# Writeup: SSTV Signal Decoding - Jerónimo Echeverri

## Overview

This project documents the process of decoding SSTV (Slow Scan Television) signals from WAV audio files. The task was part of a hardware hacking challenge where audio files contained encoded messages transmitted as SSTV signals.

## Tools Used

- **Virtual Audio Cable (VAC)**: Redirects audio output to a virtual input for processing.
- **RX-SSTV**: Decodes SSTV signals and reveals hidden images.
- **VLC Media Player/Filmora**: Plays the WAV audio files to feed the SSTV signals into RX-SSTV.

## Steps to Decode

1. **Download and Install Required Tools**:
   - Download [Virtual Audio Cable](https://software.muzychenko.net/trials/vac470.zip).
   - Install and configure VAC to redirect audio output to RX-SSTV.
   - Install RX-SSTV for decoding SSTV signals.

2. **Playback and Decoding**:
   - Use VLC/Filmora to play the WAV files.
   - RX-SSTV automatically decodes the SSTV signal as the audio plays, revealing the hidden images.

3. **Results**:
   - Successfully decoded the SSTV signals from `7.wav` and `5.wav`, obtaining the flag.

## Flag

`CTFZone{s1ng@l_dEtected!}`


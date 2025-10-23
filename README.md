ECHO WAVE_Video_Audio_Text_Audio Synthesis 
 
 1. Introduction

    •	This project implements a full pipeline to automate the process of converting YouTube videos into text and speech.

    •	It involves downloading a video, extracting its audio, transcribing the audio into text using Deepgram, and then converting that text into synthesized speech using gTTS.

2. Technologies Used
   
    • yt-dlp: For downloading YouTube videos as progressive mp4 files.
 
    • moviepy: For extracting audio from the downloaded video as .mp3 file.
  
    • Deepgram SDK: For transcribing audio into text (txt format) using AI.
  
    • gTTS: For converting the transcribed text into speech.
  
    • re, json, os: For formatting and file handling.

3. Project Workflow
   
    Step 1: Download YouTube Video
          Uses yt-dlp to download the best available progressive mp4 file.
  
    Step 2: Extract Audio using Moviespy
          Uses Moviespy to extract full-length audio from the downloaded video file.
  
   Step 3: Transcribe Audio using Deepgram
          Deepgram’s Nova-2 model is used via SDK with enhanced tier options.
          Duration is auto-detected using moviepy to ensure complete 
          .
          Output is saved in JSON format.
  
   Step 4: Convert Transcript to Clean TXT
          Text is cleaned using Python’s re module and split into sentences.
          Each sentence is saved on a new line in a .txt file.
  
  Step 5: Convert Text to Speech
          gTTS generates an mp3 audio file reading the full transcript aloud.

4. Output Files

      • video.mp4 – Downloaded YouTube video

      • extracted_audio.mp3 – Extracted full-length audio from video

      • transcript.json – Full transcription result from Deepgram

      • transcript.txt – Human-readable cleaned transcript

      • final_speech.mp3 – Audio file created from the transcript using gTTS

5. Challenges and Fixes

      • Issue: Only 17 seconds of audio was being transcribed.

      • Fix: Switched from MoviePy to FFmpeg for audio extraction and added Deepgram’s duration override.

      • Issue: ffmpeg not available in system path.

      • Fix: Avoided needing ffmpeg merge by using progressive formats via yt-dlp.


6. Conclusion

      •	This project demonstrates a robust pipeline integrating Python tools and modern AI APIs to process YouTube content for accessibility and speech synthesis.

      •	It's useful for voice-overs, subtitles, and educational audio generation.

      •	This is an upgradation of this project by upgrading from pytube module to yt-dlp

7. Future Enhancements

       • Add subtitle/timestamp support.

       • Create a Streamlit GUI version.

       • Add language translation feature.

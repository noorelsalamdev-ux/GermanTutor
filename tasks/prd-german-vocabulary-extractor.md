# Product Requirements Document: German Vocabulary Extractor

## Introduction/Overview

The German Vocabulary Extractor is a mobile application designed to help German language learners automatically extract and study vocabulary from German YouTube lessons. The app downloads audio from YouTube videos, transcribes the content using offline speech recognition, extracts German vocabulary words, provides translations and example sentences, and presents everything in an organized, exportable format.

**Problem Statement:** German learners often struggle to efficiently extract and study vocabulary from authentic German content like YouTube lessons. Manual note-taking is time-consuming and inconsistent, while existing tools lack the offline, mobile-friendly approach needed for effective learning.

**Goal:** Create a seamless, offline-capable mobile app that transforms German YouTube lessons into structured vocabulary learning materials.

## Goals

1. **Primary Goal:** Enable German learners to automatically extract vocabulary from YouTube German lessons with 95% accuracy
2. **Secondary Goal:** Provide offline functionality for core features (transcription, translation, vocabulary extraction)
3. **Tertiary Goal:** Deliver results in under 5 minutes for typical 30-minute lessons
4. **User Experience Goal:** Maintain app size under 100MB while providing comprehensive offline capabilities
5. **Accessibility Goal:** Support audio pronunciation for extracted vocabulary words

## User Stories

### Primary User Stories
- **As a German language learner**, I want to input a YouTube link to a German lesson so that I can automatically extract vocabulary without manual note-taking
- **As a German language learner**, I want to see German words with English translations and example sentences so that I can understand context and usage
- **As a German language learner**, I want to hear audio pronunciation of extracted words so that I can learn correct pronunciation
- **As a German language learner**, I want to export my vocabulary list as a PDF so that I can study offline or share with others

### Secondary User Stories
- **As a German language learner**, I want the app to work offline so that I can use it without internet connectivity
- **As a German language learner**, I want to see processing progress so that I know the app is working on longer videos
- **As a German language learner**, I want the app to filter out common words so that I focus on meaningful vocabulary

## Functional Requirements

### Core Functionality
1. **YouTube Integration**
   - The system must accept YouTube URLs as input
   - The system must download audio from YouTube videos (up to 1 hour duration)
   - The system must validate that the input is a valid YouTube URL
   - The system must handle various YouTube URL formats (youtube.com, youtu.be, etc.)

2. **Audio Processing & Transcription**
   - The system must download audio in a format compatible with Vosk ASR
   - The system must transcribe German audio using Vosk offline speech recognition
   - The system must show progress indicators during transcription
   - The system must handle audio quality variations gracefully

3. **Vocabulary Extraction**
   - The system must extract unique German words from transcribed text
   - The system must filter out German stopwords and common words
   - The system must sort extracted words by frequency of occurrence
   - The system must identify word boundaries correctly for German text

4. **Translation & Context**
   - The system must translate German words to English using Mozilla Bergamot
   - The system must generate example sentences from the original transcript context
   - The system must provide English translations for example sentences
   - The system must handle compound German words appropriately

5. **User Interface**
   - The system must display results in a clean, scrollable table format
   - The system must show German word, English translation, and example sentence for each entry
   - The system must provide audio pronunciation for each German word
   - The system must show processing progress with estimated time remaining

6. **Export Functionality**
   - The system must export vocabulary tables as PDF files
   - The system must format PDF exports as simple tables with word/translation/example columns
   - The system must allow users to save PDFs to device storage
   - The system must handle export errors gracefully

### Technical Requirements
7. **Offline Capability**
   - The system must function without internet connection for core features
   - The system must include Vosk German language model (under 100MB total app size)
   - The system must include Mozilla Bergamot German-English translation model
   - The system must cache models locally on first app launch

8. **Performance**
   - The system must process 30-minute videos in under 5 minutes
   - The system must maintain responsive UI during processing
   - The system must handle memory efficiently for long audio files
   - The system must provide progress feedback every 10% completion

## Non-Goals (Out of Scope)

1. **Multi-language Support:** The app will only process German content
2. **Video Playback:** The app will not play YouTube videos, only extract audio
3. **Social Features:** No user accounts, sharing, or collaborative features
4. **Advanced Study Tools:** No spaced repetition, flashcards, or quiz functionality
5. **Cloud Storage:** No cloud backup or synchronization features
6. **Real-time Processing:** No live transcription of ongoing videos
7. **Custom Models:** No user training or customization of ASR/translation models
8. **Multiple Export Formats:** Only PDF export, no CSV, Excel, or other formats

## Design Considerations

### User Interface
- **Input Screen:** Simple text field for YouTube URL with clear validation
- **Processing Screen:** Progress bar with percentage and estimated time remaining
- **Results Screen:** Clean table with columns for German word, English translation, example sentence, and audio button
- **Export Screen:** Simple button to generate and save PDF

### Mobile-First Design
- Optimize for portrait orientation on smartphones
- Use native mobile UI components (Flutter Material Design)
- Ensure touch-friendly button sizes and spacing
- Support both light and dark themes

### Accessibility
- Provide audio pronunciation for all extracted words
- Support screen readers with proper labeling
- Ensure sufficient color contrast for text readability
- Include haptic feedback for user interactions

## Technical Considerations

### Technology Stack
- **Framework:** Flutter for cross-platform mobile development
- **Speech Recognition:** Vosk ASR with German language model
- **Translation:** Mozilla Bergamot for German-English translation
- **PDF Generation:** pdf_flutter package
- **Audio Processing:** FFmpeg for audio format conversion
- **YouTube Integration:** youtube-dl or similar for audio extraction

### Architecture
- **Offline-First:** All core processing happens locally on device
- **Modular Design:** Separate modules for audio processing, transcription, translation, and UI
- **Error Handling:** Comprehensive error handling for network, processing, and storage issues
- **Memory Management:** Efficient handling of large audio files and model data

### Dependencies
- Vosk Android SDK for speech recognition
- Mozilla Bergamot Flutter plugin for translation
- FFmpeg Flutter plugin for audio processing
- pdf_flutter for PDF generation
- Permission handling for storage access

## Success Metrics

### Primary Metrics
1. **Accuracy:** 95% of extracted German words are correctly identified and translated
2. **Performance:** 90% of 30-minute videos processed in under 5 minutes
3. **User Adoption:** 80% of users successfully complete their first vocabulary extraction
4. **App Size:** Total app size remains under 100MB including all models

### Secondary Metrics
1. **Error Rate:** Less than 5% of processing attempts result in complete failure
2. **User Retention:** 60% of users return to use the app within one week
3. **Export Usage:** 40% of users export at least one vocabulary list as PDF
4. **Processing Success:** 95% of valid German YouTube videos are successfully processed

## Open Questions

1. **Model Updates:** How will users receive updates to Vosk and Bergamot models?
2. **Storage Management:** Should the app allow users to manage downloaded audio files?
3. **Error Recovery:** What happens if transcription fails partway through a long video?
4. **Quality Thresholds:** What minimum audio quality is required for successful transcription?
5. **Legal Compliance:** Are there any YouTube Terms of Service considerations for audio extraction?
6. **Model Licensing:** Confirm that Vosk and Bergamot models can be bundled in a commercial app
7. **Performance Optimization:** Should the app support background processing for very long videos?
8. **User Feedback:** How should users report transcription or translation errors?

---

**Document Version:** 1.0  
**Last Updated:** [Current Date]  
**Target Audience:** Junior developers implementing the German Vocabulary Extractor mobile application

# Task List: German Vocabulary Extractor

## Relevant Files

- `lib/main.dart` - Main app entry point and navigation setup
- `lib/screens/input_screen.dart` - YouTube URL input and validation screen
- `lib/screens/processing_screen.dart` - Progress display during audio processing
- `lib/screens/results_screen.dart` - Vocabulary table display with audio pronunciation
- `lib/screens/export_screen.dart` - PDF export functionality
- `lib/services/youtube_service.dart` - YouTube audio download and processing
- `lib/services/transcription_service.dart` - Vosk ASR integration for German transcription
- `lib/services/vocabulary_service.dart` - German word extraction and filtering logic
- `lib/services/translation_service.dart` - Mozilla Bergamot translation integration
- `lib/services/audio_service.dart` - Audio pronunciation and playback
- `lib/services/pdf_service.dart` - PDF generation and export functionality
- `lib/models/vocabulary_item.dart` - Data model for vocabulary entries
- `lib/models/processing_state.dart` - State management for processing workflow
- `lib/utils/audio_utils.dart` - Audio format conversion and processing utilities
- `lib/utils/german_utils.dart` - German language processing utilities (stopwords, etc.)
- `lib/widgets/vocabulary_table.dart` - Custom table widget for displaying results
- `lib/widgets/progress_indicator.dart` - Custom progress display component
- `lib/widgets/audio_player.dart` - Audio pronunciation player widget
- `test/services/youtube_service_test.dart` - Unit tests for YouTube service
- `test/services/transcription_service_test.dart` - Unit tests for transcription service
- `test/services/vocabulary_service_test.dart` - Unit tests for vocabulary extraction
- `test/services/translation_service_test.dart` - Unit tests for translation service
- `test/models/vocabulary_item_test.dart` - Unit tests for vocabulary model
- `test/widgets/vocabulary_table_test.dart` - Widget tests for table component
- `android/app/src/main/AndroidManifest.xml` - Android permissions and configuration
- `pubspec.yaml` - Flutter dependencies and project configuration
- `assets/models/vosk_model/` - Vosk German language model files
- `assets/models/bergamot_model/` - Mozilla Bergamot German-English model files

### Notes

- Unit tests should be placed alongside the code files they are testing
- Use `flutter test` to run all tests, or `flutter test test/path/to/specific_test.dart` for individual tests
- Model files will be downloaded and cached locally on first app launch
- All services should be designed for offline operation

## Tasks

- [ ] 1.0 Project Setup and Configuration
  - [ ] 1.1 Create new Flutter project with proper package structure
  - [ ] 1.2 Configure pubspec.yaml with required dependencies (vosk, bergamot, pdf_flutter, etc.)
  - [ ] 1.3 Set up Android permissions for internet, storage, and audio recording
  - [ ] 1.4 Configure Android build settings for native model integration
  - [ ] 1.5 Create assets directory structure for model files
  - [ ] 1.6 Set up proper folder structure following Flutter best practices

- [ ] 2.0 Core Data Models and State Management
  - [ ] 2.1 Create VocabularyItem model with German word, English translation, and example sentence
  - [ ] 2.2 Create ProcessingState model for tracking download, transcription, and translation progress
  - [ ] 2.3 Implement state management using Provider or Riverpod for app-wide state
  - [ ] 2.4 Create data validation and error handling for models
  - [ ] 2.5 Set up proper serialization/deserialization for data persistence

- [ ] 3.0 YouTube Audio Download Service
  - [ ] 3.1 Research and integrate YouTube audio extraction library (youtube-dl or similar)
  - [ ] 3.2 Implement URL validation for various YouTube formats
  - [ ] 3.3 Create audio download service with progress tracking
  - [ ] 3.4 Implement audio format conversion to Vosk-compatible format
  - [ ] 3.5 Add error handling for network issues and invalid URLs
  - [ ] 3.6 Implement audio file cleanup and temporary storage management

- [ ] 4.0 Speech Recognition and Transcription
  - [ ] 4.1 Download and integrate Vosk German language model
  - [ ] 4.2 Implement Vosk ASR service for offline German transcription
  - [ ] 4.3 Create audio preprocessing pipeline for optimal transcription quality
  - [ ] 4.4 Implement progress tracking for long audio files
  - [ ] 4.5 Add error handling for transcription failures and audio quality issues
  - [ ] 4.6 Optimize memory usage for large audio files during transcription

- [ ] 5.0 Vocabulary Extraction and Processing
  - [ ] 5.1 Create German stopwords list and common words filter
  - [ ] 5.2 Implement German word tokenization and boundary detection
  - [ ] 5.3 Create vocabulary extraction algorithm with frequency counting
  - [ ] 5.4 Implement compound German word handling and splitting
  - [ ] 5.5 Add word frequency sorting and filtering logic
  - [ ] 5.6 Create context extraction for generating example sentences

- [ ] 6.0 Translation Service Integration
  - [ ] 6.1 Download and integrate Mozilla Bergamot German-English model
  - [ ] 6.2 Implement Bergamot translation service for offline operation
  - [ ] 6.3 Create batch translation processing for multiple words
  - [ ] 6.4 Add translation quality validation and error handling
  - [ ] 6.5 Implement example sentence translation using Bergamot
  - [ ] 6.6 Optimize translation performance for large vocabulary lists

- [ ] 7.0 User Interface Development
  - [ ] 7.1 Create main navigation structure and routing
  - [ ] 7.2 Design and implement input screen with URL validation
  - [ ] 7.3 Create processing screen with progress indicators and time estimates
  - [ ] 7.4 Design and implement results screen with scrollable vocabulary table
  - [ ] 7.5 Create export screen with PDF generation options
  - [ ] 7.6 Implement responsive design for different screen sizes
  - [ ] 7.7 Add loading states, error messages, and user feedback
  - [ ] 7.8 Implement dark/light theme support

- [ ] 8.0 Audio Pronunciation System
  - [ ] 8.1 Integrate Flutter TTS (Text-to-Speech) for German pronunciation
  - [ ] 8.2 Configure German language TTS settings and voice selection
  - [ ] 8.3 Create audio player widget with play/pause controls
  - [ ] 8.4 Implement audio pronunciation for individual vocabulary words
  - [ ] 8.5 Add audio controls to vocabulary table (play button per word)
  - [ ] 8.6 Handle audio playback errors and device audio settings

- [ ] 9.0 PDF Export Functionality
  - [ ] 9.1 Integrate pdf_flutter package for PDF generation
  - [ ] 9.2 Create PDF template with vocabulary table layout
  - [ ] 9.3 Implement table formatting with German word, translation, and example columns
  - [ ] 9.4 Add PDF styling (fonts, colors, spacing) for professional appearance
  - [ ] 9.5 Implement file saving to device storage with user permissions
  - [ ] 9.6 Add export progress indicator and success/error feedback
  - [ ] 9.7 Handle PDF generation errors and storage permission issues

- [ ] 10.0 Testing and Quality Assurance
  - [ ] 10.1 Write unit tests for all service classes (YouTube, transcription, vocabulary, translation)
  - [ ] 10.2 Create widget tests for UI components (tables, progress indicators, audio players)
  - [ ] 10.3 Implement integration tests for complete user workflows
  - [ ] 10.4 Test offline functionality with various German YouTube videos
  - [ ] 10.5 Performance testing for large audio files and long processing times
  - [ ] 10.6 Memory usage testing and optimization
  - [ ] 10.7 Error handling testing for network issues, invalid URLs, and processing failures
  - [ ] 10.8 User acceptance testing with real German learning content

# Speaking Coach AI

![Screenshot 2025-04-03 105227](https://github.com/user-attachments/assets/e0e17c66-d338-4742-957a-fb66a8598ea7)



🎙️ **Speaking Coach AI** is an AI-powered tool designed to help users improve their presentation and speaking skills. By uploading or recording an audio file, users receive constructive feedback on their speech, including tips to enhance clarity, professionalism, and grammar. The tool uses advanced speech-to-text transcription (via Whisper) and a language model (Qwen) to analyze and provide specific, actionable suggestions.

## Features
- **Audio Transcription**: Converts spoken audio into text using OpenAI's Whisper model.
- **AI Feedback**: Provides detailed, constructive feedback on your speaking style, including suggestions for improvement and corrections for unprofessional language or grammatical errors.
- **Customizable Input**: Record audio directly via microphone or upload an audio file.
- **Topic-Based Coaching**: Specify the topic of your presentation to get tailored feedback.
- **User-Friendly Interface**: Built with Gradio for an intuitive and interactive experience.

## Installation

### Prerequisites
- Python 3.8 or higher
- A compatible environment with GPU support (optional but recommended for faster processing)

### Steps
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/speaking-coach-ai.git
   cd speaking-coach-ai
   ```

2. **Install Dependencies**:
   Install the required Python packages using the provided `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application**:
   Launch the app with the following command:
   ```bash
   python app.py
   ```

   By default, the app will run locally. To share it publicly, uncomment the `app.launch(share=True)` line in the code and run it again.

## Requirements
The following packages are required (listed in `requirements.txt`):
```
gradio
librosa
transformers
torch
```

## Usage
1. **Launch the App**: Run the script (`app.py`).
2. **Provide Input**:
   - Enter the topic of your presentation in the "Topic" textbox.
   - Record your presentation using the microphone or upload an audio file.
3. **Get Feedback**: Submit the audio and topic to receive detailed feedback in the "Speaking Coach Feedback" textbox.

### Example
- **Topic**: "The Future of Artificial Intelligence"
- **Audio Input**: Record yourself speaking about the topic.
- **Output**: Feedback such as:
  - "You used 'um' multiple times, which can distract listeners. Try pausing briefly instead."
  - "Your sentence 'AI gonna change everything' should be revised to 'AI will transform everything' for professionalism."
  - "Final suggested version: 'Artificial Intelligence will transform industries in the coming years...'"

## How It Works
![Screenshot 2025-04-03 094716](https://github.com/user-attachments/assets/d21c076a-9088-4a94-a325-e96c7a738a15)

1. **Audio Transcription**: The app uses the Whisper model (`openai/whisper-large`) to transcribe your audio into text.
2. **Feedback Generation**: The transcribed text is analyzed by the Qwen language model (`Qwen/Qwen2.5-0.5B-Instruct`), which provides constructive feedback based on a few-shot prompting template.
3. **Interface**: Gradio provides a simple web interface to interact with the tool.

## Customization
- **Model Size**: Change the `model_size` parameter in `transcribe_audio()` to `small`, `medium`, or `large` depending on your needs (default is `large`).
- **Feedback Style**: Modify the `few_shot_prompting` list in `process_audio()` to adjust the tone or specificity of the feedback.

## Limitations
- Requires a stable internet connection for initial model downloads.
- Processing time depends on audio length and hardware (faster with GPU).
- Feedback quality may vary based on audio clarity and transcription accuracy.

## Contributing
Feel free to submit issues or pull requests to improve the project! Suggestions for enhancing feedback, adding features, or optimizing performance are welcome.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.



# Kokoro TTS

A powerful command-line text-to-speech tool built on the Kokoro ONNX model, offering multilingual support, diverse voice options, and compatibility with various input formats such as EPUB books.

💡 **Try it now for free:** [https://kokorottsai.com/](https://kokorottsai.com/)

---

## Features

- **Multilingual and Voice Support**: Supports multiple languages and a variety of lifelike voices.
- **Input Formats**: Processes both EPUB and TXT files seamlessly.
- **Streaming Audio Playback**: Play audio directly without saving.
- **Chapter Splitting**: Automatically splits output into organized chapters.
- **Adjustable Speech Speed**: Fine-tune the speed for customized playback.
- **Audio Formats**: Outputs in WAV or MP3 formats.
- **Chapter Merging**: Combine existing audio chunks into complete chapters.
- **Detailed Debugging**: Offers in-depth logs for troubleshooting and optimization.

---

## Key Highlights

- **EPUB Processing**: Extract chapters, preserve structure, and create organized output for each section.
- **Audio Processing**: Manage long text, provide immediate streaming playback, and handle interruptions seamlessly.
- **Flexible Outputs**: Generate single files, split by chapters, and support multiple audio formats.
- **Debug Support**: Display detailed logs, metadata, and troubleshooting information for advanced users.

---

## Prerequisites

- **Python 3.x** installed.
- Required Python packages:  
  `soundfile`, `sounddevice`, `kokoro_onnx`, `ebooklib`, and `beautifulsoup4`.

---
## Installation

1. Clone the repository:
```bash
git clone https://github.com/nazdridoy/kokoro-tts.git
cd kokoro-tts
```

2. Install required packages:
```bash
pip install soundfile sounddevice kokoro_onnx ebooklib beautifulsoup4
```
Note: You can also use `uv` as a faster alternative to pip for package installation. (This is a uv project)

3. Download the required model files:
```bash
wget https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files/voices.json
wget https://github.com/thewh1teagle/kokoro-onnx/releases/download/model-files/kokoro-v0_19.onnx
```

## Usage

Basic usage:
```bash
./kokoro-tts <input_text_file> [<output_audio_file>] [options]
```

### Commands

- `-h, --help`: Show help message
- `--help-languages`: List supported languages
- `--help-voices`: List available voices
- `--merge-chunks`: Merge existing chunks into chapter files

### Options

- `--stream`: Stream audio instead of saving to file
- `--speed <float>`: Set speech speed (default: 1.0)
- `--lang <str>`: Set language (default: en-us)
- `--voice <str>`: Set voice (default: interactive selection)
- `--split-output <dir>`: Save each chunk as separate file in directory
- `--format <str>`: Audio format: wav or mp3 (default: wav)
- `--debug`: Show detailed debug information during processing

### Input Formats

- `.txt`: Text file input
- `.epub`: EPUB book input (will process chapters)

### Examples

```bash
# Basic usage with output file
kokoro-tts input.txt output.wav --speed 1.2 --lang en-us --voice af_sarah

# Process EPUB and split into chunks
kokoro-tts input.epub --split-output ./chunks/ --format mp3

# Stream audio directly
kokoro-tts input.txt --stream --speed 0.8

# Merge existing chunks
kokoro-tts --merge-chunks --split-output ./chunks/ --format wav

# Process EPUB with detailed debug output
kokoro-tts input.epub --split-output ./chunks/ --debug

# List available voices
kokoro-tts --help-voices

# List supported languages
kokoro-tts --help-languages
```

## Features in Detail

### EPUB Processing
- Automatically extracts chapters from EPUB files
- Preserves chapter titles and structure
- Creates organized output for each chapter
- Detailed debug output available for troubleshooting

### Audio Processing
- Chunks long text into manageable segments
- Supports streaming for immediate playback
- Progress indicators for long processes
- Handles interruptions gracefully

### Output Options
- Single file output
- Split output with chapter organization
- Chunk merging capability
- Multiple audio format support

### Debug Mode
- Shows detailed information about file processing
- Displays NCX parsing details for EPUB files
- Lists all found chapters and their metadata
- Helps troubleshoot processing issues


## Contributing

This tool is primarily designed for personal use, but contributions are welcome. If you'd like to enhance or expand it, feel free to submit a pull request.

---

## License

This project is licensed under the **MIT License**. Check the `LICENSE` file for full details.

---

## Acknowledgments

Special thanks to:  
- Kokoro ONNX model developers.  
- Contributors to the dependent libraries.

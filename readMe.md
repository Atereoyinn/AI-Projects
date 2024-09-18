# Medical Diagnostic Form Assistant

This Jupyter notebook creates a medical diagnostic form assistant that transcribes medical conversations and extracts key information to fill out a diagnostic form.

## Features

- Audio transcription using Whisper
- Entity extraction for patient details (name, age, gender)
- Medical entity extraction (symptoms, diagnosis, medical history, action plan)
- User-friendly Gradio interface
- CSV export functionality

## Setup

1. Open the notebook in a Jupyter environment with GPU support (e.g., Google Colab).
2. Run the first cell to install required packages:
   ```
   !pip install transformers accelerate faster-whisper bitsandbytes gradio
   ```
3. Run subsequent cells to import modules and initialize models.

## Usage

1. Execute all cells in order.
2. The last cell launches a Gradio interface with a "share" link for remote access.
3. Upload an audio file or record audio directly in the interface.
4. The system will process the audio and display extracted information.
5. Use the "Download CSV" button to export results.

## Models Used

- Whisper (large-v3) for audio transcription
- NuExtract-tiny for basic entity extraction
- Fine-tuned Llama model for medical entity extraction

## Notes

- Ensure you have sufficient GPU resources to run the models.
- Processing time may vary based on audio length and system capabilities.
- This tool is for demonstration purposes and should not replace professional medical advice.
look at my readMe.md file






### 2. llama3-finetuned-for-medical-entity-extraction.ipynb

This notebook contains the process for fine-tuning the LLaMA model for medical entity extraction. It includes:

- Data preparation
- Model fine-tuning
- Evaluation of the fine-tuned model

The resulting model is used in the user interface for extracting medical entities from transcribed audio.

## Setup and Usage

1. Install the required dependencies:
   ```
   pip install transformers accelerate bitsandbytes datasets trl peft torch
   ```
2. Authenticate with Hugging Face using your API access token.
3. Configure the model for quantization using bitsandbytes.
4. Load the pre-trained LLaMA model and tokenizer with the quantized configuration.
5. Set up PEFT (Parameter-Efficient Fine-Tuning) configuration for the model.
6. Load and preprocess the "har1/MTS_Dialogue-Clinical_Note" dataset from Hugging Face.
7. Fine-tune the model using the prepared dataset.
8. Evaluate the fine-tuned model and run inference tests.
9. Merge the fine-tuned adapter with the base model.
10. Save the final model and upload it to Hugging Face for easy access in the main application.

Note: This process requires significant computational resources and may take several hours to complete, depending on your hardware configuration.
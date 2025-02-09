# GPT-4o Object Detection

## Overview

This project utilizes the GPT-4o model for object detection within images stored in a specified folder. It leverages the advanced capabilities of GPT-4o to analyze images and identify objects, providing detailed insights and classifications. This tool is designed for researchers, developers, and hobbyists interested in exploring object detection capabilities powered by one of the most advanced AI models available.

## Features

- **Batch Processing**: Efficiently processes images in bulk.
- **Advanced Object Detection**: Uses GPT-4o AI for detailed object identification.
- **Customizable Outputs**: Flexible output formatting for easy integration.
- **Enhanced Logging**: Logs images, responses, and request times for performance analysis.
- **User-Friendly**: Streamlined setup and operation.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.8 or higher installed on your system.
- Access to GPT-4o API and the necessary API keys (refer to the [`.env`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FRepositiories%2Fthd-cart-detection%2F.env%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Repositiories\thd-cart-detection\.env") file setup below).
- All required Python packages installed (see the `requirements.txt` file).

## Setup

1. **Clone the Repository**: Clone this repository to your local machine using `git clone`.

2. **Install Dependencies**: Navigate to the project directory and install the required Python packages using:

   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Environment Variables**: Create a `.env` file in the project root with the following variables:

   ```dotenv
   GPT_4o_ENDPOINT=https://example.com/
   GPT_4o_API_KEY=your_api_key_here
   GPT_4o_API_VERSION=your_api_version_here
   GPT_4o_CHAT_DEPLOYMENT_NAME=your_deployment_name_here
   GPT_4o_CHAT_MODEL=your_model_here
   ```

   Replace the placeholder values with your actual GPT-4o API endpoint, API key, API version, deployment name, and model.

## Usage

To use the GPT-4o Object Detection tool, follow these steps:

1. **Prepare Your Images**: Place all the images you want to analyze in the designated image folder.

2. **Run the Script**: Execute the main script ([`main.py`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FRepositiories%2Fthd-cart-detection%2Fmain.py%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Repositiories\thd-cart-detection\main.py")) from your terminal or command prompt:

   ```bash
   python main.py
   ```

3. **View Results**: The script will process each image and output the detection results. The results can be found in the specified output directory or console, based on your configuration.

## Optimizations

- Processing multiple images in one single request to the model might be more optimal. You’re essentially batching the images together. This means that instead of making separate API calls for each image (which would each have their own overhead costs such as network latency, server processing time, etc.), you make a single API call that includes all the images.
- URLs are easier to manage and reuse, especially when dealing with multiple images over extended interactions, and for that reason OpenAI suggests passing images via URL's instead of base64
- The latency of the model can also be improved by downsizing your images ahead of time to be less than the maximum size they are expected them to be. For low res mode, we expect a 512px x 512px image. For high res mode, the short side of the image should be less than 768px and the long side should be less than 2,000px. (https://platform.openai.com/docs/guides/vision/managing-images)
- General guidance on reducing latency: [The LLM Latency Guidebook: Optimizing Response Times for GenAI Applications - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/ai-azure-ai-services-blog/the-llm-latency-guidebook-optimizing-response-times-for-genai/ba-p/4131994)


## Contributing

Contributions to this project are welcome. Please follow the standard fork-and-pull request workflow. If you plan to introduce a major change, it's best to open an issue first to discuss it.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

This project is made possible by the advanced capabilities of the GPT-4o model and the OpenAI API. Special thanks to the OpenAI team for providing access to such powerful tools.
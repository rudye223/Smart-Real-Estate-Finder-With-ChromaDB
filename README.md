
# Smart Real Estate Finder with Text, Image and Video Search

## Overview
The **Smart Real Estate Finder** is an innovative application that allows users to find properties based on various inputs, including text queries, images, videos or a combination of them. The application utilizes advanced AI models for image and video processing and ChromaDB as the vector search database ensuring accurate and relevant results.

## Features
- **Multi-Modal Search**: Search properties using text queries, images, videos or a combination.
- **Real-Time Results**: Get instant property matches and details.
- **User-Friendly Interface**: Easy-to-navigate interface designed for optimal user experience.
- **Gallery View**: View similar properties in a gallery format.


## Installation and Setup

To run this project locally, follow these steps:

 
### Clone the Repository

```bash
git clone https://github.com/Im-in123/aptos-dapp-rock-paper-scissors
cd chromadb-text-to-image

```
 
Create a Python virtual environment to manage the project's dependencies by running the following command on your terminal:
```bash
 python3 -m venv .venv
```

Now, activate the virtual environment:

On macOS/ Linux:
```bash
 
source .venv/bin/activate
```

On Windows:
```bash
.venv\Scripts\activate
```

With the virtual environment activated, install the necessary dependencies by running this command:
```bash
 
pip install -r requirements.txt
```
Launch the application by running the script:
```bash
python3 app.py
```


## Requirements
- Python 3.7 or higher
- Required packages:
  - `torch`
  - `transformers`
  - `PIL`
  - `gradio`
  - `opencv-python`
  - `chromadb`
  - `numpy`
  - `pysqlite3`



Ensure you have a JSON file (property_data.json) containing your property data in the following format:

```json
 
{
    "properties": [
        {
            "id": "1",
            "description": "A beautiful house in the countryside.",
            "price": "300000",
            "address": "123 Country Lane",
            "features": ["garden", "garage", "swimming pool"],
            "image": "path/to/image1.jpg"
        },
        ...
    ]
}
```

## How to Use the Application

### Accessing the Application

Launch the application by navigating to the provided local URL after running the application script.

### Input Options

Users have three main input options to perform searches:

#### A. Text Query
- **Description**: Type in keywords related to the property you are looking for, such as the type of property, features, or location.
- **Example Queries**:
  - "2-bedroom apartment in downtown"
  - "Pet-friendly house with garden"
  - "Luxury villa with ocean view"

#### B. Image Upload
- **Description**: Upload an image of a property or similar properties to find matches based on visual similarity.
- **Example Uses**:
  - Upload a picture of a property you like.
  - Use an image of a property brochure or listing.

#### C. Video Upload
- **Description**: Upload a video that showcases a property. The app will extract frames to generate embeddings for comparison.
- **Example Uses**:
  - A video tour of a property.
  - A clip showcasing neighborhood features.

### Search Combinations

Users can utilize different combinations of the input options to refine their search:

- **Text Only Search**:  
  Input text query in the text box. Leave the image and video upload fields empty.  
  _Example_: "Spacious condo near beach."

- **Image Only Search**:  
  Upload an image in the image upload field. Leave the text box and video upload field empty.  
  _Example_: Upload an image of a desired property.

- **Video Only Search**:  
  Upload a video in the video upload field. Leave the text box and image upload field empty.  
  _Example_: Upload a video showcasing a property tour.

- **Text and Image Search**:  
  Enter a text query and upload an image. Leave the video upload field empty.  
  _Example_: "Modern apartment" with an image of a similar apartment.

- **Text and Video Search**:  
  Enter a text query and upload a video. Leave the image upload field empty.  
  _Example_: "House with pool" with a video of a house with a pool.

- **Image and Video Search**:  
  Upload both an image and a video. Leave the text box empty.  
  _Example_: Upload a photo and video of a property you are interested in.

- **Text, Image, and Video Search**:  
  Input a text query, upload an image, and upload a video.  
  _Example_: "3-bedroom house" with an image and a video showcasing the house.

### Viewing Results

After submitting a query, users will see:

- **Best Match Image**: The property image that best matches the search criteria.
- **Best Match Details**: Information about the best match, including description, price, and address.
- **Similar Properties Gallery**: A gallery showcasing up to four similar properties for comparison.

### Tips for Effective Searches

- **Be Specific**: The more specific your text query, the better the results. Include details like the number of bedrooms, price range, and unique features.
- **Use Clear Images**: Ensure that the images you upload are clear and well-lit for better matching.
- **Relevant Videos**: Upload videos that directly showcase the property of interest for optimal results.

```bash
#error with chroma  workaround 
# first: pip install pysqlite3-binary
# then add the code below in your py file:
# these three lines swap the stdlib sqlite3 lib with the pysqlite3 
import pysqlite3
import sys
sys.modules['sqlite3'] = sys.modules.pop('pysqlite3')
```

## Acknowledgments

This project makes use of the following technologies:

- **Hugging Face Transformers**
- **OpenAI CLIP**
- **VideoMAE**

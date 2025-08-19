# Channel-Transcript-Data-Pipeline
Automate the extraction and structuring of YouTube video transcripts. Simply set up your Apify API key, YouTube channel URL, and Google Sheets/Docs credentials to collect, translate, and store video data effortlessly. Ideal for creating a knowledge base from YouTube content.

## YouTube Transcript Extractor Workflow

### 1. **Manual Trigger**
The workflow begins with a **manual trigger** that allows the user to start the process when needed.

### 2. **Get Data from YouTube Channel**
The first node retrieves data from the **YouTube channel** of Dr. Zeeshan Usmani using the **Apify API**. It fetches the list of videos along with metadata such as:
- Video Title
- Video URL
- View Count
- Duration
- Date Posted  
The **YouTube channel link** and **API key** are pre-set to target Dr. Zeeshan Usmani's channel.

### 3. **Get Video Transcript**
The **HTTP request node** interacts with the **YouTube Transcript API** to fetch the transcript of each video in **English**. The transcript is extracted using the video ID passed to the API.

### 4. **Data Cleaning**
A **cleaning node** is used to extract the relevant parts of the transcript using **CSS selectors**. This ensures that only the transcript text is captured.

### 5. **Data Structuring and Translation (Optional)**
The **Langchain agent node** receives the video title and transcript. If the transcript is in a language other than English, it **translates the content** to simple English.  
The agent then **structures the content** by organizing the transcript into headings, subheadings, and bullet points, ensuring it is easy to follow.

### 6. **Store Data in Google Sheets**
After structuring the transcript, the relevant metadata and cleaned data (e.g., video title, view count, transcript) are **appended to Google Sheets** for record-keeping and analysis. This sheet can be updated in real-time.  
The metadata includes:
- Video Title
- Video ID
- View Count
- Duration
- Video URL
- Posting Date

### 7. **Generate HTML and Update Google Docs**
The structured transcript is **converted into HTML format** for easy reading and presentation.  
This HTML content, along with the metadata (e.g., video title and view count), is inserted into a **Google Doc** for further processing or manual edits.  
The Google Doc is updated with each new transcript and video, creating a comprehensive knowledge base.

### 8. **Final Steps**
After processing a batch of videos, the workflow updates the **Google Sheet** or **Google Doc** with the status, marking which videos have been processed.  
The workflow includes a **5-second wait node** before moving to the next video or completing the process.

---

## Key Features:
- **Automated Transcript Extraction:** The workflow automatically fetches and cleans the transcript for each video.
- **Data Structuring:** Transcripts are organized into a readable format with headings and bullet points.
- **Google Sheets and Docs Integration:** Data is stored in Google Sheets for easy access and in Google Docs for documentation.
- **Translation:** Non-English transcripts are automatically translated into simple English.
- **Error Handling and Retries:** The workflow is designed to handle errors and retry fetching data if necessary.

<img width="665" height="658" alt="Screenshot 2025-08-18 at 5 47 24 PM" src="https://github.com/user-attachments/assets/c0342d09-2c79-4ec3-bcec-aef9aa41e5a9" />

## Steps to Run the Workflow:

### 1. Set Up Apify API
- You need to set up your **Apify API key** in the workflow. This will allow the workflow to fetch data from the specified YouTube channel.
- You can obtain your **Apify API key** from the [Apify dashboard](https://apify.com/streamers/youtube-channel-scraper).

### 2. Set Up YouTube Channel URL
- Replace the default channel URL (`https://www.youtube.com/@zusmani78`) with the YouTube channel URL of the creator whose videos you want to extract.
- Ensure the URL is correct to avoid fetching data from the wrong channel.

### 3. Google Sheets Integration
- Set up **[Google Sheets](https://docs.google.com/spreadsheets/d/1Jp92APk_iGa1XlYRJQBpFOFFWRMAZ_n-a3bEuvnyg_A/edit?usp=sharing) API credentials** and authenticate the connection within the workflow.
- Provide the correct **Google Sheets document ID** and **sheet name** where the video metadata will be saved.
- This allows the workflow to append processed data like video titles, view counts, and transcript details into your Google Sheets.

### 4. Google Docs Integration
- Set up **Google Docs API credentials** and authenticate the connection within the workflow.
- Provide the **Google Docs document ID** where the structured and processed video transcript data will be stored.
- Each video will be added to the Google Docs, either by appending or updating the content.

### 5. Test the Workflow
- After setting up the credentials and configurations, **test the workflow** to ensure that everything is working as expected.
- You can manually trigger the workflow and check if the transcript and video data are being saved properly in the Google Sheets and Docs.

### 6. Customize Settings
- You can customize the workflow to handle different video channels, or adjust the number of results fetched by the Apify scraper, depending on your needs.
- You can also set the number of items to be processed (e.g., the first 200 videos) by adjusting the **maxItems** setting.

After setting up the workflow, you can simply go to **Google DeepMind** at [https://notebooklm.google.com/](https://notebooklm.google.com/) and upload all your documents there. Enjoy chatting with the knowledge of your favorite YouTuber's videos in a personal, interactive way!

<img width="1728" height="913" alt="Screenshot 2025-08-19 at 6 00 54 AM" src="https://github.com/user-attachments/assets/c5266a32-5b2f-4667-b395-386bbda08795" />


## Conclusion:
This workflow provides a fully automated solution for extracting and organizing YouTube video transcripts. It's perfect for creating a knowledge base, enhancing productivity, and streamlining content processing from YouTube. Whether you're managing content for a single channel or multiple, this workflow ensures easy access to video metadata and transcripts in both Google Sheets and Docs. 


---

Feel free to customize the workflow according to your needs and enjoy seamless transcript extraction and organization! and chatting with the knowledge of your favorite YouTuber's videos in a personal, interactive way!



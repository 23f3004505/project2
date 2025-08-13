# TDS Data Analyst Agent

**Overview**

TDS Data Analyst Agent is a comprehensive API-based application developed for automatically solving data analysis tasks from the *Tools in Data Science* course at **IIT Madras**. The API uses Large Language Models and various data processing tools to analyze data, create visualizations, and provide intelligent responses to complex analytical questions.

## Features

✅ **Multi-format Data Processing** - Handles CSV, ZIP, JSON, and various file formats  
✅ **Web Scraping** - Extracts data from Wikipedia and other web sources  
✅ **Database Integration** - Supports DuckDB for large-scale data analysis  
✅ **Visualization Generation** - Creates plots and charts as base64 encoded images  
✅ **LLM Integration** - Uses GPT-4 for intelligent question analysis  
✅ **Real-time Analysis** - Processes requests within 3-minute timeout  
✅ **Scalable Deployment** - Deployed on Vercel for global accessibility  

## API Usage

### Endpoint
```
POST https://your-deployed-url.vercel.app/api/
```

### Request Format

**Headers:** `Content-Type: multipart/form-data`

**Form Data:**
- `questions.txt` *(file, required)* – Text file containing the analysis questions
- Additional files *(optional)* – CSV, ZIP, or other data files for analysis

### Example Requests

**Wikipedia Analysis:**
```bash
curl -X POST "https://your-deployed-url.vercel.app/api/" \
  -F "questions.txt=@questions.txt"
```

**Data File Analysis:**
```bash
curl -X POST "https://your-deployed-url.vercel.app/api/" \
  -F "questions.txt=@questions.txt" \
  -F "data.csv=@dataset.csv" \
  -F "image.png=@chart.png"
```

### Example Response

**For Wikipedia Films Analysis:**
```json
[1, "Titanic", 0.485782, "data:image/png;base64,iVBORw0KG..."]
```

**For Court Judgments Analysis:**
```json
{
  "Which high court disposed the most cases from 2019 - 2022?": "Delhi High Court",
  "What's the regression slope...": "0.0234",
  "Plot the year and # of days...": "data:image/png;base64,..."
}
```

## Supported Analysis Types

- **Web Scraping**: Wikipedia tables, news articles, APIs
- **Statistical Analysis**: Correlations, regressions, trend analysis
- **Data Visualization**: Scatter plots, time series, histograms
- **Large Dataset Processing**: DuckDB integration for 16M+ records
- **File Processing**: CSV parsing, ZIP extraction, Excel analysis
- **Time Series Analysis**: Date calculations, trend identification

## Technical Architecture

- **Backend**: Flask (Python)
- **AI Integration**: OpenAI GPT-4 via AI Proxy
- **Data Processing**: Pandas, NumPy, DuckDB
- **Visualization**: Matplotlib, Seaborn
- **Web Scraping**: BeautifulSoup, Requests
- **Deployment**: Vercel Serverless Functions

## Installation & Local Development

1️⃣ **Clone the repository:**
```bash
git clone https://github.com/23f3004505/project2.git
cd project2
```

2️⃣ **Install dependencies:**
```bash
pip install -r requirements.txt
```

3️⃣ **Set up environment variables:**
```bash
export OPENAI_API_KEY="your_api_key_here"
```

4️⃣ **Run locally:**
```bash
python app.py
```

The API will be available at `http://localhost:8000`

## Deployment

This project is deployed on **Vercel** for serverless execution and global accessibility.

**Deploy your own:**
1. Fork this repository
2. Connect to Vercel
3. Set environment variables
4. Deploy automatically

## Performance Specifications

- **Response Time**: < 3 minutes (as required)
- **File Size Limits**: Images < 100KB, Data files < 10MB
- **Concurrent Requests**: Supports multiple simultaneous analysis tasks
- **Retry Logic**: Built-in error handling with 4 retry attempts

## License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---

**Created by Yuvraj Singh Mor** | **IIT Madras** | **Tools in Data Science 2025**

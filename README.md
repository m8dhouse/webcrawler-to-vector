# web crawler-to-vector
Python web crawler script to upload vector data to Upstash or DataStax. Uses openAI text-embedding-3-small embedding model but can be easily adapted.
Version with HuggingFace integration and model BERTje (can be easily changed) also there as example.


#READ.ME

Small Python script that scans a given URL (depth configurable), crawls each link it finds and scrapes the text content.
The crawler only scans text, it explicitly ignores links to images, pdf, dmg, ... 

The scraped text content is then chopped into chunks (size and overlap configurable) to be processed by openAI 
embeddings model text-embedding-3-small.

The resulting vector data is then uploaded into UpStash or DataStax Astra.

I created this as neither of these platforms have any decent tutorials/examples that I could find for processing and uploading scraped webdata.


Feel free to adapt to your needs.

UpStash: has a free plan as well. Very fast ... 
DataStax: has a larger free plan that should be ok for small websites.


There is a startup.py file that reads the requirements.txt so that you have all the required libraries installed.

=====================================================

DATASTAX ASTRA -> change the variable placeholders with your key/url/secret
    
    # Configuration variables
    OPENAI_API_KEY = '<YOUR KEY>'
    START_URL = '<URL TO CRAWL>'
    ASTRA_CLIENT_ID = '<CLIENT_ID>'
    ASTRA_CLIENT_SECRET = '<ASTRA_SECRET>'
    ASTRA_DB_API_ENDPOINT = '<ASTRA_ENDPOINT>'
    CHUNK_SIZE = 1000
    OVERLAP = 200
    MAX_DEPTH = 3
    KEYSPACE = 'default_keyspace'
    COLLECTION = '<COLLECTION NAMEN>'


=====================================================

UPSTASH -> change the variable placeholders with your key/url/secret

    # Configuration variables
    OPENAI_API_KEY = '<YOUR KEY>'
    START_URL = '<URL TO CRAWL>'
    UPSTASH_TOKEN = '<UPSTASH_TOKEN>'
    UPSTASH_API_ENDPOINT = '<UPSTASH_ENDPOINT>'
    CHUNK_SIZE = 1000
    OVERLAP = 200
    MAX_DEPTH = 3
    COLLECTION = '<COLLECTION NAME>'

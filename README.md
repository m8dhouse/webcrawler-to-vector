# webcrawler-to-vector
Python webcrawler script to upload vector data to Upstash or DataStax. Uses openAI text-embedding-3-small embedding model but can be easily adapted.


#READ.ME

Small Python script that scans a given URL (depth configurable), crawls each link it finds and scrapes the text content.
The crawler only scans text, it explicitly ignores links to images, pdf, dmg, ... 

The scraped text content is then chopped into chunks (size and overlap configurable) to be processed by openAI 
embeddings model text-embedding-3-small.

The resulting vector data is then uploaded into UpStash or DataStax Astra.

I created this as neither of these platforms have any decent tutorials/examples for processing and uploading scraped webdata.


Feel free to adapt to your needs.

UpStash: you have a fairly small Free plan - so ideally if you want to use this you'll need to go for the paid plan.
DataStax: has a larger free plan that should be ok for small websites.


There is a startup.py file that reads the requirements.txt so that you have all the required libraries installed.
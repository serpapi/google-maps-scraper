# Google Maps Scraper

[<img width="950" height="300" alt="Google Maps scraper tool" src="https://github.com/user-attachments/assets/2f1d195b-0fe8-4e18-a3fa-89bcf7f7c956" />](https://serpapi.com/google-maps-api?utm_source=github_google_maps_scraper)

Google Maps Scraper - A tool to scrape map results with a simple API. Get place information like GPS coordinates, reviews, rating, type, operating hours, and more.

We provide the results in a structured JSON format, eliminating the need for parsing, coding, proxies, or any other web scraping headaches for developers.

Here is the response example:
<img width="1209" height="457" alt="scrape Google Maps" src="https://github.com/user-attachments/assets/a0dcb87b-6bbb-47ec-bdb0-c902036e180f" />

## How to scrape Google Maps?

Using a simple GET request, you can retrieve Google Maps search results:

```
https://serpapi.com/search.json?engine=google_maps&q=Coffee&ll=@40.7455096,-74.0083012,14z&api_key=YOUR_API_KEY
```

- Register for free at [SerpApi to get your API Key](https://serpapi.com/google-maps-api?utm_source=github_google_maps_scraper)
- `q` parameter:  defines the query you want to search.
- `ll` parameter: defines the GPS coordinates of the location where you want the search to originate from. Its value must match the following format:
`@ + latitude + , + longitude + , + zoom/map_height`

The zoom attribute ranges from 3z, map completely zoomed out - to 21z, map completely zoomed in. Alternatively, you can specify map_height in meters (e.g., 10410m).

## Code examples
Here are some code examples based on your favorite programming languages.

### cURL Integration

```
curl --get https://serpapi.com/search \
 -d engine="google_maps" \
 -d q="Coffee" \
 -d ll="@40.7455096,-74.0083012,14z" \
 -d api_key="secret_api_key"
```

### Python Integration

Preparation for accessing the SerpApi API in Python

Step 1:  
Create a new `main.py` file. (You can name it whatever you want)

Step 2:  
Install [requests package](https://pypi.org/project/requests/) with:
```
pip install requests
```

Step 3:  
Add this code to your file:
``` py
import requests
SERPAPI_API_KEY = "YOUR_SERPAPI_API_KEY"

params = {
    "api_key": SERPAPI_API_KEY, 
    "engine": "google_maps",
    "q": "coffee",
    "ll": "@40.7455096,-74.0083012,14z"
}

search = requests.get("https://serpapi.com/search", params=params)
response = search.json()
print(response)
```

If you're only interested in the `local_results`, you can print them from the response directly. It's an array of places:

``` py
print(response["local_results"])
```

> Warning: Sometimes, this API returns `place_results` instead of `local_results` if Google Maps returns a specific place


### JavaScript Integration

Step 1:  
Install the [SerpApi JavaScript package](https://github.com/serpapi/serpapi-javascript):
```
npm install serpapi
```

Step 2:  
Create a new `index.js` file. (You can name it whatever you want)

Step 3:  
Add this to your file for basic search:
``` js
const { getJson } = require("serpapi");
getJson({
  api_key: API_KEY, // Put your API Key
  engine: "google_maps",
  q: "coffee",
  ll: "@40.7455096,-74.0083012,14z"
}, (json) => {
  console.log(json["local_results"]);
});
```

We're printing the `local_results` from Google Maps in this case.

### Other Programming Languages
While you can use our APIs using a simple GET request with any programming language, you can also see our ready-to-use libraries here: [SerpApi Integrations](https://serpapi.com/integrations?utm_source=github_google_maps_scraper).

### Google Maps Scraper Parameter

Please find the parameters for this API below:

| Name          | Description                                                                                                                                                                                                                | Requirement |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| q             | Parameter defines the query you want to search                                                                                                                                                                             | Required    |
| ll            | Parameter defines the GPS coordinates of the location where you want the search to originate from. Its value must match the following format: @ + latitude + , + longitude + , + zoom/map_height                           | Required    |
| Localization  |                                                                                                                                                                                                                            |             |
| google_domain | Parameter defines the Google domain to use. It defaults to google.com                                                                                                                                                      | Optional    |
| hl            | Parameter defines the language to use for the Google Maps search. It's a two-letter language code. (e.g.,en for English, es for Spanish, or fr for French).                                                                | Optional    |
| gl            | Parameter defines the country to use for the Google Maps search. It's a two-letter country code. (e.g.,us for the United States, uk for United Kingdom, or fr for France).                                                 | Optional    |
| Pagination    |                                                                                                                                                                                                                            |             |
| start         | Parameter defines the result offset. It skips the given number of results. It's used for pagination. (e.g., 0 (default) is the first page of results, 20 is the 2nd page of results, 40 is the 3rd page of results, etc.). | Optional    |
|               | Visit our docs for more                                                                                                                                                                                                    |             |

## Blog tutorial 
- [Scrape Google Maps data and reviews using Python](https://serpapi.com/blog/scrape-google-maps-data-and-reviews-using-python/)
- [No-Code Google Maps Scraper options](https://serpapi.com/blog/no-code-google-maps-scraper-options-2/)

Interesting use cases:
- [How AI Can Predict the Success of Your Business Using Data from Google Maps](https://serpapi.com/blog/how-ai-can-predict-the-success-of-your-business-using-data-from-google-maps/)
- [How To Make a Travel Guide Using SERP data and Python](https://serpapi.com/blog/how-to-make-a-travel-guide-using-serp-data-and-python/)
- [Gauge Business Popularity using Google Maps](https://serpapi.com/blog/gauge-business-popularities-using-google-maps/)

## Video tutorial
- [Scrape Google Maps reviews data using Python](https://www.youtube.com/watch?v=naigldB0nTY)
- [Scrape unlimited leads in one click (Collect data from Google Maps)](https://www.youtube.com/watch?v=20IidkHRqDA)

## Contacts
Feel free to reach out via `contact@serpapi.com`.

Check other [Google Scraper](https://github.com/serpapi/google-scraper) from SerpApi.


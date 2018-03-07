# WebScraper

It's responsible for web scraping by using google chrome headless in background.

## Requirement

Node.js > 8.x or docker machine

## Run API

### Manual 

```bash
git clone git@github.com:digestoo/web-scraper.git
cd web-scraper
npm install
PORT=8080 npm start
```

You can use additional environment variables once running API with npm:

- `EXECUTABLE_PATH` - path to custom google chrome (you can find it in chrome://version)
- `USER_DATA_DIR` - path to user profile
- `SLOW_MO` - slow down operations by specified amount of ms
- `HEADLESS=false` - run server in headfull mode
- `USER_AGENT` - global user agent
- `PORT`

### Docker

```bash
docker pull cigolpl/web-scraper
docker run -it -p 8080:8080 cigolpl/web-scraper
```

## Making requests

```bash
curl -XGET -H "Content-Type: application/json" -d '{"url":"'http://stackoverflow.com/questions/3207418/crawler-vs-scraper'","pageFunction":"function($) { return { title: $(\"title\").text() }}","userAgent":"WebScraper"}' http://localhost:8080
```
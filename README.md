# Challenge 10: Mission-to-Mars

# Overiew of Mission to Mars
In this project, Splinter and BeautifulSoup are used to scrape four different websites:
- 'https://mars.nasa.gov/news/': to retrieve news title and new paragraph.
- 'https://data-class-jpl-space.s3.amazonaws.com/JPL_Space/index.html': to retreive the URl for the featured image.
- 'http://space-facts.com/mars/': to retrieve a table on Mars facts.
- 'https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars: to retrieve full-resolution images of Mars’s hemispheres and the titles of those images.

The code could be found in [Mission_to_Mars_Challenge]().

The scraped data is stored in mars_app Mongo database in mars collection, the document looks as follows:
![]()




Flask - Python web farmework - in used to display the scraped data stored in Mongo, and also to display any updates on the webpage when scraping is triggered. This code for Flask could be found in [app.py](). Flask uses the scraping code found in [scraping.py]() and renders the webpage according to the html found in [index.html]().

For Deliverable 3,
- The webpage is mobile responsive, here is a screenshot of how the webpage would appear in Phone6/7/8:


- This tables  following Bootstrap 3 components to style the webpage, this can be found in [index_style.html](). Here are the changes introduced:

| Element | Addition | Addition Desciption  | html Altered |
| :---: | :---: | :---: | :---: |
| "Scrape New Data" button | ```class="btn-block"```| makes the button span the full width of the prent elemnt | ```<p><a class="btn btn-primary btn-block btn-lg" href="/scrape" role="button">Scrape New Data</a></p>```| 
| "Mars Facts" Header | ```<strong>Mars Facts</strong>```| bolds the text in the header | ```<div class="row" id="mars-facts">
            <h4><strong>Mars Facts</strong></h4>
            {{ mars.facts | safe }}
          </div>```|
| "Mars Facts" Header | ```<strong>Mars Facts</strong>"```| bolds the text in the header | ```<div class="row" id="mars-facts"> <h4><strong>Mars Facts</strong></h4{{ mars.facts | safe }}</div>```|


the entire html can be found in 



 


# Challenge 10: Mission-to-Mars

# Overiew of Mission to Mars
In this project, Splinter and BeautifulSoup are used to scrape four different websites:
- https://mars.nasa.gov/news/: to retrieve news title and new paragraph.
- https://data-class-jpl-space.s3.amazonaws.com/JPL_Space/index.html: to retreive the URl for the featured image.
- http://space-facts.com/mars/: to retrieve a table on Mars facts.
- https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Marsß: to retrieve full-resolution images of Mars hemispheres and the titles of those images.

The code for scraping the above websites could be found in [Mission_to_Mars_Challenge](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Mission_to_Mars_Challenge.ipynb).

The scraped data is stored in mars_app Mongo database in mars collection, the document looks as follows:
![]()

Flask - Python web farmework - in used to display the scraped data stored in Mongo, and also to display any updates on the webpage when scraping is triggered. This code for Flask could be found in [app.py](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/app.py). Flask uses the scraping code found in [scraping.py](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/scraping.py) and renders the webpage according to the html found in [index.html](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/templates/index.html).

In Deliverable 1, the list of dictionary items:
![]() 

In Deliverable 2,


For Deliverable 3,
- The webpage is mobile responsive, here is a screenshot of how the webpage would appear in Phone6/7/8:
![]()

- This table summarizes Bootstrap 3 components that were added to style the webpage, these changes can be found in [index_styles.html](). Here are the changes introduced:

| Element | Addition | Addition Desciption | html Altered |
| :---: | :---: | :---: | :---: |
| "Scrape New Data" Button | ```class="btn-block"```| makes the button span the full width of the parent element | ```<p><a class="btn btn-primary btn-block btn-lg" href="/scrape" role="button">Scrape New Data</a></p>```| 
| "Mars Facts" Header | ```<strong>Mars Facts</strong>```| bolds the text in the header | ```<h4><strong>Mars Facts</strong></h4>``` |
| "Mars Facts" Table | ```return df.to_html(classes="table table-striped")```| converts dataframe into HTML format and adds bootstrap class to add zebra-stripes to the table| In scarping.py, replace the return statement in ```def mars_facts()```|
| "Mars Hemispheres" Images | ```class="img-thumbnail img-circle" width="304" height="236"```| "img-thumbnail" shapes the image to a thumbnail and "img-circle" class shapes the image to a circle | ```<img src="{{hemisphere.img_url | default('static/images/error.png', true)}}" class="img-thumbnail img-circle" width="304" height="236" alt="...">``` |


 


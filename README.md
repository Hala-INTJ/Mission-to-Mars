# Challenge 10: Mission-to-Mars

# Overiew of Mission to Mars
In this project, Splinter and BeautifulSoup are used to scrape four different websites:
- https://mars.nasa.gov/news/: to retrieve news title and news paragraph.
- https://data-class-jpl-space.s3.amazonaws.com/JPL_Space/index.html: to retreive the URL for the featured image.
- http://space-facts.com/mars/: to retrieve a table on Mars facts.
- https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars: to retrieve full-resolution images of Mars hemispheres and the titles of those images.
## Deliverable 1
The code for scraping the above websites is in [Mission_to_Mars_Challenge.ipynb](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Mission_to_Mars_Challenge.ipynb). The scraped data is stored in the **mars_app** Mongo database in the **mars** collection.

A screenshot of the list of dictionary items:

![](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Resources/List%20of%20dictionaries.png)
## Deliverable 2
Flask - Python web framework - provides a button to initiate scraping data and displays the results stored in Mongo. The Flask code is in [app.py](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/app.py). Flask uses the scraping code in [scraping.py](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/scraping.py) and renders the webpage using the html template in [index.html](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/templates/index.html).

A screenshot of the webpage after scraping the data:

![](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Resources/webpage_scraped_data.png)
## Deliverable 3
The webpage is mobile-responsive. Here are screenshots displaying the webpage on multiple devices:

| iPad | iPhone 6/7/8 |
| --- | --- |
| ![](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Resources/iPad.png) | ![](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Resources/iPhone7.png) |

This table summarizes the Bootstrap 3 components which were added to style the webpage. These changes can be found in [index_styled.html](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/templates/index_styled.html).

| Element | Addition | Addition Desciption |
| :---: | :---: | :---: |
| "Scrape New Data" Button | ```class="btn-block"```| makes the button span the full width of the parent element | 
| "Mars Facts" Header | ```<strong>Mars Facts</strong>```| bolds the text in the header | 
| "Mars Facts" Table | ```return df.to_html(classes="table table-striped")```| converts dataframe into HTML format and adds bootstrap CSS class to add zebra-stripes to the table, this change is in [scraping.py](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/scraping.py)| 
| "Mars Hemispheres" Images | ```class="img-thumbnail img-circle" width="304" height="236"```| "img-thumbnail" shapes the image to a thumbnail and "img-circle" class shapes the image to a circle |
| "Mars Hemispheres" Four Across | ```<div class="col-md-3">```| Divides the row into four equal width columns |

 A screenshot of the webpage after applying these styling changes:

 ![](https://github.com/Hala-INTJ/Mission-to-Mars/blob/main/Resources/webpage_index_styled.png)
# Random Wikipedia walker

Using Selenium, create a small program that, starting from the main page https://www.wikipedia.org/, walks trough a sequence of random links and takes a snapshot of the last page.
The process is as follows:

 1. Navigate to the main page https://www.wikipedia.org/
 2. Select a random link in the page
 3. Navigate to the link
 4. Repeat steps 2 to 3 until you have visited 10 different pages
 5. Take a snapshot of the current page and save it

Include the code of the walker and the snapshot in this document.

## Answer
HAMONO Hermine et ROY Raphaẽl 
![screenshot](https://user-images.githubusercontent.com/119609091/224297929-b6baa0dc-5a62-4dd6-84c3-fed8eaeffaa0.png)*

 ```
from selenium import webdriver
import random

from selenium.webdriver.common.by import By

browser = webdriver.Firefox()
browser.get("https://www.wikipedia.org/")


for i in range(10):
    links = browser.find_elements(By.XPATH, "//a[@href]")
    random_index = random.randint(0, len(links) - 1)
    random_link = links[random_index]
    link_url = random_link.get_attribute("href")
    browser.get(link_url)

browser.save_screenshot("screenshot.png")

browser.quit()
```

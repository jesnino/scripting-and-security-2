# Realizar una búsqueda y pulsar sobre un enlace en Chrome desde Python
## Python 
### URL: https://www.jesusninoc.com/2018/01/24/realizar-una-busqueda-y-pulsar-sobre-un-enlace-en-chrome-desde-python/
```Python
import time
from selenium import webdriver

driver = webdriver.Chrome()
driver.get('http://www.google.com');
search_box = driver.find_element_by_name('q')
search_box.send_keys('python')
search_box.submit()
findElem = driver.find_element_by_link_text('Welcome to Python.org')
findElem.click()
time.sleep(5)
driver.quit()

```

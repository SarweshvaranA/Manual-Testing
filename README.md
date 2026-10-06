# Manual-Testing


## Test plan - Excel sheet

https://1drv.ms/x/c/ab623637ed28c1bc/IQDKRG6u2sIYTbmO5HWx8aN7AcQEOkC3fEyna3Dq8OjEB0o?e=LBbMg9&nav=MTVfezc5NkFDNzcyLThCNkItNDE4Qi1CQTcwLTExNDBDOEM2MDQ1M30


## Test case - Exercises

https://1drv.ms/x/c/ab623637ed28c1bc/IQA2GZAuf709QJ0DZPbZpmSCAc2zUClU2kPag__AKXKEuP8?e=vqL66w

### 24/09 - TASK

https://1drv.ms/x/c/ab623637ed28c1bc/IQCzC6Z4nHQTSbvODFY1JjAvAWwIwPXfKdnBn74Uxd6ZI9g?e=jagTZf


### 25/09 - Task

https://colab.research.google.com/drive/1tD0uqMfyjD8dmgKNn0MOQ1cRqv0gGeii?usp=sharing

### 29/09 - Task

https://colab.research.google.com/drive/1wS6yAqA6eeRpBGIU-EJ9LX3oTlg_D7aJ?usp=sharing


## AUTOMATOIN TESTING
###  6/10 - Task

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver.get("https://vinothqaacademy.com/demo-site-sit/")

time.sleep(5)
first_name=driver.find_element(By.ID,"vfb-5")
first_name.send_keys("Sarweshvaran")

last_name=driver.find_element(By.ID,"vfb-7")
last_name.send_keys("Anand")

gender=driver.find_element(By.ID,"vfb-31-1").click()


course=driver.find_element(By.ID,"vfb-20-0").click()
time.sleep(2)

address=driver.find_element(By.ID,"vfb-13-address")
address.send_keys("keelkattalai")
time.sleep(2)

street=driver.find_element(By.ID,"vfb-13-address-2")
street.send_keys("parry colony")
time.sleep(2)

suite=driver.find_element(By.ID,"vfb-13-city")
suite.send_keys("suite")
time.sleep(2)

city=driver.find_element(By.ID,"vfb-13-zip")
city.send_keys("Chennai")
time.sleep(2)

email=driver.find_element(By.ID,"vfb-14")
email.send_keys("sarweshvaran.a@gmail.com")
time.sleep(20)
```


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3fda58d7-9c7c-4eff-bd2f-2875086a2ffe" />

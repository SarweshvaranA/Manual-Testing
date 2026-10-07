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



### 6/10 - TASK 2

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

driver = webdriver.Edge()
driver.maximize_window()

wait = WebDriverWait(driver, 20)
driver.get("https://www.amazon.in/")


login = wait.until(
    EC.element_to_be_clickable(
        (By.CLASS_NAME, "nav-line-1-container")
    )
)
login.click()


phone = wait.until(
    EC.visibility_of_element_located(
        (By.NAME, "email")
    )
)
phone.send_keys("7397225410")


cont = wait.until(
    EC.element_to_be_clickable(
        (By.CLASS_NAME, "a-button-input")
    )
)
cont.click()

otp = wait.until(
    EC.visibility_of_element_located(
        (By.NAME, "code")
    )
)

otp.send_keys(input("Enter OTP: "))


otp_button = wait.until(
    EC.element_to_be_clickable(
        (By.CLASS_NAME, "a-button-input")
    )
)
otp_button.click()

print("Login successful")


search = wait.until(
    EC.visibility_of_element_located(
        (By.ID, "twotabsearchtextbox")
    )
)

search.send_keys("Mens shoes")


search_button = wait.until(
    EC.element_to_be_clickable(
        (By.ID, "nav-search-submit-button")
    )
)
search_button.click()

print("Product searched")

time.sleep(4)


buttons = driver.find_elements(
    By.XPATH,
    '//button[@aria-label="Add to cart"]'
)

print("Add to cart buttons found:", len(buttons))


for button in buttons:
    if button.is_displayed() and button.is_enabled():
        driver.execute_script(
            "arguments[0].scrollIntoView({block: 'center'});",
            button
        )
        time.sleep(1)
        button.click()
        print("Product added to cart")
        break

else:
    print("No enabled Add to cart button found.")


time.sleep(3)

driver.get("https://www.amazon.in/gp/cart/view.html")
print("Cart opened")
time.sleep(4)


checkout = wait.until(
    EC.element_to_be_clickable(
        (By.NAME, "proceedToRetailCheckout")
    )
)

checkout.click()
print("Checkout opened")
time.sleep(5)

try:

    payment = wait.until(
        EC.element_to_be_clickable(
            (By.NAME, "ppw-instrumentRowSelection")
        )
    )

    payment.click()
    print("Payment method selected")

except:
    print("Payment method was not found")


input("Press Enter to close browser...")
driver.quit()
```

<img width="1456" height="1078" alt="image" src="https://github.com/user-attachments/assets/118a975a-1dc3-4087-88f8-15150b5ffb77" />

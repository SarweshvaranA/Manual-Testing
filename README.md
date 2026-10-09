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



### 7/10 - TASK

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

driver = webdriver.Chrome()
driver.maximize_window()

wait = WebDriverWait(driver, 10)

driver.get("https://www.saucedemo.com/")

print("TC01 - Shopping website opened successfully")

wait.until(
    EC.visibility_of_element_located((By.ID, "user-name"))
).send_keys("standard_user")

driver.find_element(By.ID, "password").send_keys("secret_sauce")
driver.find_element(By.ID, "login-button").click()

wait.until(
    EC.visibility_of_element_located((By.CLASS_NAME, "inventory_list"))
)

print("TC01 - Login successful")


driver.get("https://www.selenium.dev/selenium/web/alerts.html")

driver.find_element(By.ID, "alert").click()

alert = wait.until(
    EC.alert_is_present()
)

print("\nTC02 - Alert:")
print(alert.text)

alert.accept()

print("TC02 - Product deletion confirmed")


driver.get("https://www.selenium.dev/selenium/web/alerts.html")

driver.find_element(By.ID, "confirm").click()

alert = wait.until(
    EC.alert_is_present()
)

print("\nTC03 - Confirmation Alert:")
print(alert.text)

alert.dismiss()

print("TC03 - Product remains in the cart")


driver.get("https://www.selenium.dev/selenium/web/alerts.html")

driver.find_element(By.ID, "prompt").click()

alert = wait.until(
    EC.alert_is_present()
)

print("\nTC04 - Prompt Alert:")
print(alert.text)

alert.send_keys("SARWESHVARAN ")
alert.accept()

print("TC04 - Customer information submitted successfully")


driver.get("https://www.selenium.dev/selenium/web/mouse_interaction.html")

hover_element = wait.until(
    EC.visibility_of_element_located((By.ID, "hover"))
)

ActionChains(driver).move_to_element(hover_element).perform()

move_status = wait.until(
    EC.visibility_of_element_located((By.ID, "move-status"))
)

print("\nTC05 - Mouse Hover performed successfully")
print("Result:", move_status.text)


driver.get("https://www.selenium.dev/selenium/web/mouse_interaction.html")

double_click_element = wait.until(
    EC.visibility_of_element_located((By.ID, "clickable"))
)

ActionChains(driver).double_click(double_click_element).perform()

click_status = wait.until(
    EC.visibility_of_element_located((By.ID, "click-status"))
)

print("\nTC06 - Double Click performed successfully")
print("Result:", click_status.text)


driver.get("https://www.selenium.dev/selenium/web/mouse_interaction.html")

source = wait.until(
    EC.visibility_of_element_located((By.ID, "draggable"))
)

target = wait.until(
    EC.visibility_of_element_located((By.ID, "droppable"))
)

ActionChains(driver).drag_and_drop(source, target).perform()

drop_status = wait.until(
    EC.visibility_of_element_located((By.ID, "drop-status"))
)

print("\nTC07 - Drag and Drop performed successfully")
print("Result:", drop_status.text)


driver.get("https://www.automationexercise.com/products")

search_box = wait.until(
    EC.visibility_of_element_located((By.ID, "search_product"))
)

search_box.clear()
search_box.send_keys("Top")

search_button = wait.until(
    EC.element_to_be_clickable((By.ID, "submit_search"))
)

search_button.click()

searched_products = wait.until(
    EC.visibility_of_element_located(
        (
            By.XPATH,
            "//h2[contains(translate(normalize-space(.), 'abcdefghijklmnopqrstuvwxyz', 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'), 'SEARCHED PRODUCTS')]"
        )
    )
)

products = wait.until(
    EC.presence_of_all_elements_located(
        (
            By.XPATH,
            "//div[contains(@class,'productinfo')]"
        )
    )
)

print("\nTC08 - Product search completed successfully")
print("Result:", searched_products.text)
print("Number of products found:", len(products))


driver.get("https://www.saucedemo.com/")

wait.until(
    EC.visibility_of_element_located((By.ID, "user-name"))
).send_keys("standard_user")

driver.find_element(By.ID, "password").send_keys("secret_sauce")
driver.find_element(By.ID, "login-button").click()

wait.until(
    EC.visibility_of_element_located((By.CLASS_NAME, "inventory_list"))
)

driver.find_element(
    By.ID, "add-to-cart-sauce-labs-backpack"
).click()

driver.find_element(
    By.CLASS_NAME, "shopping_cart_link"
).click()

wait.until(
    EC.visibility_of_element_located((By.CLASS_NAME, "cart_item"))
)

driver.find_element(By.ID, "checkout").click()

wait.until(
    EC.visibility_of_element_located((By.ID, "first-name"))
).send_keys("SARWESHVARAN")

driver.find_element(By.ID, "last-name").send_keys("A")
driver.find_element(By.ID, "postal-code").send_keys("600117")

driver.find_element(By.ID, "continue").click()

finish_button = wait.until(
    EC.element_to_be_clickable((By.ID, "finish"))
)

print("\nTC09 - Place Order button is clickable")

finish_button.click()

confirmation = wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "complete-header")
    )
)

print("TC09 - Order submitted successfully")
print("Result:", confirmation.text)


driver.get("https://www.saucedemo.com/")

wait.until(
    EC.visibility_of_element_located((By.ID, "user-name"))
).send_keys("standard_user")

driver.find_element(By.ID, "password").send_keys("secret_sauce")
driver.find_element(By.ID, "login-button").click()

wait.until(
    EC.visibility_of_element_located((By.CLASS_NAME, "inventory_list"))
)

driver.find_element(
    By.ID, "add-to-cart-sauce-labs-backpack"
).click()

driver.find_element(
    By.CLASS_NAME, "shopping_cart_link"
).click()

wait.until(
    EC.visibility_of_element_located((By.CLASS_NAME, "cart_item"))
)

driver.find_element(By.ID, "checkout").click()

wait.until(
    EC.visibility_of_element_located((By.ID, "first-name"))
).send_keys("SARWESHVARAN")

driver.find_element(By.ID, "last-name").send_keys("A")
driver.find_element(By.ID, "postal-code").send_keys("600117")

driver.find_element(By.ID, "continue").click()

finish_button = wait.until(
    EC.element_to_be_clickable((By.ID, "finish"))
)

finish_button.click()

wait.until(
    EC.visibility_of_element_located(
        (By.CLASS_NAME, "complete-header")
    )
)

driver.execute_script(
    "setTimeout(function(){alert('Order confirmation successful')}, 500)"
)

alert = wait.until(
    EC.alert_is_present()
)

print("\nTC10 - Order Confirmation Alert:")
print(alert.text)

alert.accept()

print("TC10 - Confirmation alert handled successfully")

time.sleep(2)

driver.quit()

print("\nAll test cases completed successfully")
```

<img width="1600" height="855" alt="image" src="https://github.com/user-attachments/assets/9533b009-3c5e-46eb-b470-a53edc913397" />



### 9/10 - TASK

```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
driver = webdriver.Edge()
wait = WebDriverWait(driver, 10)
driver.get("https://assertqa.com/practice/webtables")
driver.maximize_window()
table = wait.until(
EC.visibility_of_element_located((By.TAG_NAME, "table"))
)
headers = table.find_elements(By.XPATH, ".//thead/tr/th")
rows = table.find_elements(By.XPATH, ".//tbody/tr")

print("TC01: Column Headings")
for header in headers:
print(header.text)’’
time.sleep(10)

print("TC02: First Data Row")
if rows:
print(rows[0].text)
else:
print("No data rows found")
time.sleep(10)

print("TC03: Last Data Row")
if rows:
print(rows[-1].text)
else:
print("No data rows found")

print("TC04: Search by Last Name")
last_name = input("Enter employee last name: ")
found = False
for row in rows:
if last_name.lower() in row.text.lower():
print("Matching record:", row.text)
found = True
if not found:
print("No matching employee found")

print("TC05: All Email Addresses")
for row in rows:
cells = row.find_elements(By.TAG_NAME, "td")
for cell in cells:
if "@" in cell.text:
print(cell.text)

print("TC06: Highest Due Amount")
highest_due = None
highest_due_row = None
for row in rows:
cells = row.find_elements(By.TAG_NAME, "td")
for index, header in enumerate(headers):
if header.text.strip().lower() == "due":
due_index = index
break
else:
due_index = None
if due_index is not None and due_index < len(cells):
due_text = cells[due_index].text.strip()
due_value = float(
due_text.replace("$", "").replace(",", "")
)
if highest_due is None or due_value > highest_due:
highest_due = due_value
highest_due_row = row.text
if highest_due_row is not None:
print("Employee record:", highest_due_row)
print("Highest Due amount:", highest_due)
else:
print("Due column or valid Due values not found")

print("TC07: Verify Website Link")
website = input("Enter website URL or text to search: ")
links = driver.find_elements(By.XPATH, "//a")
link_found = False
for link in links:
href = link.get_attribute("href") or ""
text = link.text.strip()
if website.lower() in href.lower() or website.lower() in text.lower():
link_found = True
print("PASS: Website link exists")
print("Link:", href)
break
if not link_found:
print("FAIL: Website link does not exist")

print("\nTC08: Count Data Rows")
print("Total data rows:", len(rows))
```




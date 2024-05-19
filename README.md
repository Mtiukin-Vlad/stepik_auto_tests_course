from selenium import webdriver
from selenium.webdriver.common.by import By
import time 

link = "http://suninjuly.github.io/simple_form_find_task.html"

try:
    browser = webdriver.Chrome()
    browser.get(link)
    
    # Поиск по имени тега
    input1 = browser.find_element(By.TAG_NAME, "input")
    # тут я отправлю текст Ivan в переменную инпут, котрую мы нашли рание 
    input1.send_keys("Ivan")

    # Поиск по имени
    input2 = browser.find_element(By.NAME, "last_name")
    input2.send_keys("Petrov")

    # Поиск по имени класса
    input3 = browser.find_element(By.CLASS_NAME, "city")
    input3.send_keys("Smolensk")

    # Поиск по айди
    input4 = browser.find_element(By.ID, "country")
    input4.send_keys("Russia")

    # Поиск по селектору
    button = browser.find_element(By.CSS_SELECTOR, "button.btn")
    
    # команда клика
    button.click()

finally:
    # успеваем скопировать код за 30 секунд
    time.sleep(30)
    # закрываем браузер после всех манипуляций
    browser.quit()

# не забываем оставить пустую строку в конце файла


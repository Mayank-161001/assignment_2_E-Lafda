# assignment_2_E-Lafda
#Selenium imports here
import time
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By
from selenium.webdriver.support.wait import WebDriverWait
from selenium.webdriver.support.ui import WebDriverWait
import getpass


#Other imports here
import os
import wget
import urllib#download krne me use

driver = webdriver.Chrome('C:/Users/mayan/chromedriver.exe')#root path lege jo prompt me dikha rha 
driver.get("https://twitter.com/elonmusk")#jo website open krni

log_in=driver.find_element(By.XPATH,"//*[@id='layers']/div/div[1]/div/div/div/div/div[2]/div/div/div[1]/a/div/span/span").click()

user_id = 'mayank39581575'
my_password = getpass.getpass()

user_name = driver.find_element(By.XPATH,"//*[@id='layers']/div[2]/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div[2]/div/div/div/div[5]/label/div/div[2]/div/input")
user_name.send_keys(user_id)


next=driver.find_element(By.XPATH,"//*[@id='layers']/div[2]/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div[2]/div/div/div/div[6]/div/span/span").click()

password = driver.find_element(By.XPATH,"//*[@id='layers']/div[2]/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div[2]/div[1]/div/div/div[3]/div/label/div/div[2]/div[1]/input")
password.send_keys(my_password)

log_in=driver.find_element(By.XPATH,"//*[@id='layers']/div[2]/div/div/div/div/div/div[2]/div[2]/div/div/div[2]/div[2]/div[2]/div/div[1]/div/div/div/div/span/span").click()

driver.get("https://twitter.com/elonmusk")

iterator = 0
for k in range(1,20):
    driver.execute_script("window.scrollBy(0,400);")
    time.sleep(5)
    twitt = driver.find_elements(By.CSS_SELECTOR,"div.css-1dbjc4n")
    print("start")
    print(twitt[0].text)
    #     [i.text for i in twitt if i.text != '']
    iterator = iterator + 1
    print(iterator)
    print("end")
    



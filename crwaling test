import os
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time

driver = webdriver.Chrome('/Users/sungjin/Desktop/code/chromedriver')
driver.get('https://steamcommunity.com/app/860890/reviews/?browsefilter=toprated&snr=1_5_100010_')


elem = driver.find_element_by_tag_name("body")
seemore = driver.find_element_by_xpath('//*[@id="GetMoreContentBtn"]/a')
end = driver.find_element_by_xpath('//*[@id="NoMoreContent"]/div[2]/a')

while True:
    elem.send_keys(Keys.PAGE_DOWN)
    time.sleep(1.0)
    if end:
        html = driver.page_source
        soup = BeautifulSoup(html, "html.parser")
        print(soup)
        break
    if seemore:
        driver.find_element_by_xpath('//*[@id="GetMoreContentBtn"]/a').click()

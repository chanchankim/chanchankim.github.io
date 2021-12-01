# chanchankim.github.io

#beijing.py

from selenium import webdriver

import time

import os

doc=open('log.txt','w')

for i in range(1,2):

	print("第",i,"次")
	#print("第",i,"次",file=doc)
	driver = webdriver.Chrome()
	driver.maximize_window()
	driver.get("https://www.baidu.com")

	print('Before search======================')
	#print('Before search======================',file=doc)

	print(driver.title)
	print(driver.current_url)
	print(driver.page_source)
	print(driver.get_cookie)
	#print(driver.title,file=doc)
	#print(driver.current_url,file=doc)
	#print(driver.page_source,file=doc)
	#print(driver.get_cookie,file=doc)

	el = driver.find_element_by_name("wd")
	el.send_keys(u"北京\n")
	#el.send_keys("北京")
	#driver.find_element_by_id("su").click()
	time.sleep(2)

	print('After search======================')
	#print('After search======================',file=doc)

	print(driver.title)
	print(driver.current_url)
	#print(driver.title,file=doc)
	#print(driver.current_url,file=doc)
	driver.back()
	time.sleep(2)
	driver.forward()
	time.sleep(2)

	driver.execute_script('window.scrollTo(0,document.body.scrollHeight)')
	time.sleep(2)
	driver.execute_script('alert("To Bottom")')
	time.sleep(2)

	driver.quit()
	os.system("pause")


















---
layout: post
title: Ravioli Ravioli Give Me The Hypoallergenic Formuoli
---

I have a hungry baby who needs a specific type of hypoallergenic formula. Instead of spending *MINUTES* per day looking for formula on every store website, I decided to spend *HOURS* creating a python code to do all the searching for me.

# Setup

I originally wanted to use Pythons Beautiful soup, but it just grabs HTML. I learned quickly that I need to interact with javascript and therefore Selenium is the ideal package for my use.
Selenium is pretty easy to [setup](https://www.selenium.dev/documentation/webdriver/getting_started/) into python iusing pip.
Selenium needs a web driver, I chose [gecodriver](https://github.com/mozilla/geckodriver/releases).

I DuckDuckGo'ed "Selenium example code" (Kidding I googled it). I just had to switch out web drivers and it worked!

    from selenium import webdriver

    driver = webdriver.Firefox()
    driver.implicitly_wait(5)
    driver.maximize_window()
    driver.get("https://www.tutorialspoint.com/about/about_careers.htm")
    l=driver.find_element_by_xpath("//a[@title='Tutorialspoint']")
    l.click()
    print("Current page title: " + driver.title)
    driver.quit()


# Lessons learned

My [code](https://github.com/EdTComeau/Formula/blob/master/main.py) is pretty horrid. But I made it fast and it works.
Here is what I learned:
- I couldnt get Selenium's implicitly_wait() to work 100% of the time. Ideally it should give time for a page to load before I make references to it. pythons time.wait(3) did the trick for my internet connection. I had use this A LOT!
- Selenium's [docs](https://selenium-python.readthedocs.io/locating-elements.html) is pretty close to the best order to reference attributes in the DOM. 
- Never use XPATH as a reference, its trash
- In firefox inspector, you can right click an item and copy its CSS_SELECTOR ![Copy a CSS Selector](\images\CSSselector.png)
- Walmart detects that I am a Beep Boop ROBOT. Sneaky! I took this as a sign I wasn't welcome and stopped, although I'm sure I could outsmart them if I wanted /s

# The final Product

When the code is done running, I have a few tabs to click through that shows me a bunch of formula and where it can be found near me. 
Selenium, is fun. 
I remember back in college a friend of mine made a script that checks for when grades are posted and sends him an email, that made him a programming god to me. He still is, but now selenium makes me feel like a programming god too. 
I dont do web stuff, making this blog is the last time I thought about HTML/CSS/JS, so this was fun to see how much there is out there that I don't YET know. 

![tabs](\images\FinalProdFormula.png)

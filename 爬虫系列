import os
import re
import requests
import urllib.request
from bs4 import BeautifulSoup
temp='F:/代码'
os.chdir(temp)
def saveimg(items):
    temp='F:/代码'
    os.chdir(temp)
    count = 1
    for item in items:
        print('一张美女图片已经保存')
        count += 1
        filename = str(count)+'.jpg'
        u = urllib.request.urlopen(item)
        data = u.read()
        f = open(filename,'wb')
        f.write(data)
def get_url():
    num = int(input('请问你要爬几页'))
    for i in (1963-num,1964):
        page = i
        url = 'http://jandan.net/ooxx/page-'+str(page)+'#comments'
        saveimg(get_img(url))


def get_img(url):
    wb_data = requests.get(url)
    soup=BeautifulSoup(wb_data.text,'lxml').prettify()
    pattern = re.compile('img src="(.*?)"',re.S)
    items = re.findall(pattern,soup)


    return items

if __name__ =='__main__':
    get_url()
    print('爬完了 快去看看')

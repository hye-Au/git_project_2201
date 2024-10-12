# git_project_2201
import urllib.request

h= {
    "Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,"
              "*/*;q=0.8,application/signed-exchange;v=b3;q=0.7",
    "Accept-Encoding": "gzip, deflate",
    "Accept-Language": "zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6",
    "user-agent": "Mozilla/5.0 (Windows NT 10.0; win64; x64) AppleWebKit/537.36 (KHTML, Like Gecko) "
              "Chrome/128.0.0.0 Safari/537.36"

}
req = urllib.request.Request("http://httpbin.org/get",headers=h)
proxies = {"http= 192.168.26.102 ": " 51382"}
proxy_handler = urllib.request.ProxyHandler(proxies=proxies)
opener = urllib.request.build_opener(proxy_handler)
r = opener.open(req)
print(r.read().decode())


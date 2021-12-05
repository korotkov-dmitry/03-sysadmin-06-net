# Домашнее задание к занятию "3.6. Компьютерные сети, лекция 1"

## 1. Работа c HTTP через телнет.
- Подключитесь утилитой телнет к сайту stackoverflow.com
`telnet stackoverflow.com 80`
- отправьте HTTP запрос
```bash
GET /questions HTTP/1.0
HOST: stackoverflow.com
[press enter]
[press enter]
```
- В ответе укажите полученный HTTP код, что он означает?

Результат:

    `vagrant@vagrant:~$ telnet stackoverflow.com 80
    Trying 151.101.193.69...
    Connected to stackoverflow.com.
    Escape character is '^]'.
    GET /questions HTTP/1.0
    HOST: stackoverflow.com

    HTTP/1.1 301 Moved Permanently
    cache-control: no-cache, no-store, must-revalidate
    location: https://stackoverflow.com/questions
    x-request-guid: 2ee65083-4bc7-44ad-8bfe-5fc4d601ecd1
    feature-policy: microphone 'none'; speaker 'none'
    content-security-policy: upgrade-insecure-requests; frame-ancestors 'self' https://stackexchange.com
    Accept-Ranges: bytes
    Date: Sun, 05 Dec 2021 10:27:43 GMT
    Via: 1.1 varnish
    Connection: close
    X-Served-By: cache-fra19160-FRA
    X-Cache: MISS
    X-Cache-Hits: 0
    X-Timer: S1638700063.494519,VS0,VE93
    Vary: Fastly-SSL
    X-DNS-Prefetch-Control: off
    Set-Cookie: prov=07644e29-d26a-61f5-3b17-951f195a586d; domain=.stackoverflow.com; expires=Fri, 01-Jan-2055 00:00:00 GMT; path=/; HttpOnly
    
    Connection closed by foreign host.`
    
Ответ сервера: `HTTP/1.1 301 Moved Permanently` - код перенаправления протокола передачи гипертекста (HTTP) показывает, что запрошенный ресурс был перемещён в URL, указанный в заголовке Location.
## 2. Повторите задание 1 в браузере, используя консоль разработчика F12.
- откройте вкладку `Network`
- отправьте запрос http://stackoverflow.com
- найдите первый ответ HTTP сервера, откройте вкладку `Headers`
- укажите в ответе полученный HTTP код.
- проверьте время загрузки страницы, какой запрос обрабатывался дольше всего?
- приложите скриншот консоли браузера в ответ.

Результат:

Status Code: `307 Internal Redirect`
    
Самый долгий запрос: 
    
    `Request URL: https://stackoverflow.com/
    Request Method: GET
    Status Code: 200 
    Remote Address: 151.101.129.69:443
    Referrer Policy: strict-origin-when-cross-origin`
    
![stackoverflow](https://user-images.githubusercontent.com/92984527/144743131-3591cb0a-d829-4325-89c3-d00198db869c.png)

## 3. Какой IP адрес у вас в интернете?
## 4. Какому провайдеру принадлежит ваш IP адрес? Какой автономной системе AS? Воспользуйтесь утилитой `whois`
## 5. Через какие сети проходит пакет, отправленный с вашего компьютера на адрес 8.8.8.8? Через какие AS? Воспользуйтесь утилитой `traceroute`
## 6. Повторите задание 5 в утилите `mtr`. На каком участке наибольшая задержка - delay?
## 7. Какие DNS сервера отвечают за доменное имя dns.google? Какие A записи? воспользуйтесь утилитой `dig`
## 8. Проверьте PTR записи для IP адресов из задания 7. Какое доменное имя привязано к IP? воспользуйтесь утилитой `dig`

В качестве ответов на вопросы можно приложите лог выполнения команд в консоли или скриншот полученных результатов.

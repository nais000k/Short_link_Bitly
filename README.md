# Сокращение ссылок с помощью BITLY 
TODO: Скрипт сокращает переданную ссылку с помощью BITLY API, либо возвращает количество переходов по сокращенной ссылке, если она была передана в качестве аргумента.

### Как установить
Для работы скрипта вы должны иметь установленный интерпретатор Python3. Затем загрузите зависимости с помощью "pip" (либо "pip3", в случае конфликтов с Python2):  
`-pip install -r requirements.txt`

Для работы скрипта необходим персональный ключ – "токен". Он нужен для взаимодействия с API Bitly. Токен выглядит как строка наподобие следующей: 17c09e20ad155405123ac1977542fecf00231da7. Bitly предлагает несколько видов токенов. Вам нужен GENERIC ACCESS TOKEN, который можно получить на странице документации Bitly:
[bitly.com](https://bitly.com/a/oauth_apps)

Регистрируйтесь на Bitly через e-mail вместо социальных сетей. Это упростит получение токена.

Необязательно читать документацию до конца. Когда вы найдёте, как создать нужный токен, можете просто переходить к его созданию.

Полученный токен храните в файле с расширением .env, который используется для сокрытия важной информации.

В коде создайте глобальную переменную, которая будет хранить в себе информацию о токене, получая её через метод os.getenv(""). Например `BITLY_TOKEN = os.getenv("BITLY_TOKEN")`, где название в кавычках - это переменная в файле .env

### Как использовать
В скрипте используется встроенная библиотека argparse. Поэтому для его корректной работы необходимо вводить ссылку либо битлинк в качестве аргумента командной строки. 

Пример для сокращения ссылки:  
`python main.py https://google.com`
Получения количества переходов по битлинку:  
`python main.py bit.ly/2JzwCxg`

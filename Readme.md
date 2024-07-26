# Crawler (тестовое задание)

## Описание

Crawler обходит веб-страницы, извлекая текст из параграфов и проверяя наличие целевой ссылки. Для управления обходом он использует стек.

## Как это работает

- **Инициализация**: Приложение запрашивает у пользователя начальный и целевой URL и создает начальный и целевой узлы
- **Создание краулера**: Инициализируется краулер с заданной максимальной глубиной обхода (представлена в виде костанты)
- **Ограничение глубины**: Переходит по ссылкам на страницах до заданной глубины
- **Поиск**: Краулер обрабатывает узлы из стека, пока стек не станет пустым или не будет найдена целевая ссылка
- **Обход**: При посещении страницы извлекаются параграфы в формате HTML, параграфы делятся на предложения (также в формате HTML), в предложениях ищутся ссылки, при нахождении ссылки преобразуем HTML в предложение в понятный текст и сохраняем данные
- **Проверка целевого узла**: Если ссылка совпадает с целевым URL, краулер завершает работу и выводит путь до целевой страницы
- **Декодирование URL**: Корректно обрабатывает и декодирует URL-адреса
- **Логирование**: Все посещенные URL записываются в лог-файл

## Установка и запуск

1. Для запуска нужно установить необходимые библиотеки:
   ```sh
   go get github.com/gocolly/colly
   go get github.com/PuerkitoBio/goquery
   ```
2. Склонируйте репозиторий:
```sh
git clone https://github.com/RomanMalashenkov/crawler.git
cd cmd/crawler
```
3. Запустите приложение:
```sh
go run main.go
```
4. Введите начальный и целевой URL по запросу приложения.

## Технологии

- [Go](https://golang.org/) — основной язык программирования
- [Colly](http://go-colly.org/) — веб-скрапер и краулер
- [Goquery](https://github.com/PuerkitoBio/goquery) — парсер HTML

# Тяжелая промышленность и .NET

Если вы хотите запрограммировать промышленную станцию, поточную линию или целый завод, а может быть, просто поуправлять рукой большого человекоподобного робота, — вам нужны специальные языки программирования. Посмотрим, как и зачем они так выглядят, и есть ли у них связь с миром классического программирования на примере C#.NET

![Title Slide](slides/00.png)

__Место проведения:__ Vladimir Tech Talks #27, г. Владимир, ул. Гагарина 5, этаж 4, [конф. зал Альтенара](https://yandex.ru/maps/-/CDQlNY~U).

31 января 2025 года. ▶ [Видео `VK`](https://vkvideo.ru/video-178974757_456239062?t=1m57s)

## План

- Упоминание позапрошлого VTT #25 и домашней автоматизации.
- "Бас-фактор" и почему в промышленности нет места самоделкам.
- Что внутри у ПЛК?
- Зачем нужны специальные языки программирования.
- Релейные-лестничные диаграммы.
- Функциональные блоки.
- Диаграммы последовательностей.
- Структурированный текст.
- Ввод-вывод.
- Машина времени и сверхточные тайминги.
- Связь с внешним миром.
- Немного о .NET сбоку.
- Как управлять роборукой.
- Визитка.

### Доп. секция

- G-code.
- Конфигуратор задач и мультиядерность.
- Подробнее о языке ST.

## Вопросы

Вопросов не было.

## Hints

### Get PNG slides with ImageMagick

> sudo apt-get install imagemagick

### ImageMagic PDF restrictions

> convert-im6.q16: attempt to perform an operation not allowed by the security policy `PDF' @ error/constitute.c/IsCoderAuthorized/408.

- Open `/etc/ImageMagick-6/policy.xml`
- Change policy for PDF: `<policy domain="coder" rights="read | write" pattern="PDF" />`

### HowTo get PNG slides

> convert -density 200 foo.pdf ./slides/foo_%02d.png

Produces series of PNG files like: `foo_00.png`, `foo_01.png`, ...

### WSL2 does not have an internet

Actualy, that is a wrong configuration of nameserver.

```shell
sudo rm /etc/resolv.conf
sudo bash -c 'echo "nameserver 1.1.1.1" > /etc/resolv.conf'
sudo bash -c 'echo "[network]" > /etc/wsl.conf'
sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'
sudo chattr +i /etc/resolv.conf
```

**Файл с переводами** к игре King of The Castle для использования с плагином [XUnity Auto Translator](https://github.com/bbepis/XUnity.AutoTranslator)

## TL;DR

* Установите игру
* Скачайте и установите плагин XUnity Auto Translator в игру
* Настройте плагин
* Запустите игру, чтобы проверить, что автоперевод на лету работает
* Если работает, закройте игру
* Скачайте файл с переводом и поместите его в папку *\steamapps\common\King of the Castle\AutoTranslator\Translation\ru\Text*
* Можно играть
* (рекомендуется) Зарегистрируйте аккаунт в DeepL (DeepL API Free) и настройте его использование в Auto Translator


## О плагине XUnity Auto Translator

Предназначен для игр на движке Unity. При установке он встраивается в игру и ведет автоперевод текстов, появляющихся на экране.

А именно:
* перехватывает текст 
* ищет перевод в файле(-ах)
* если перевод не найден, то отправляет его на один из сервисов для перевода (DeeplTranslate, GoogleTranslate, ...)
* заменяет текст на экране на переведенный
* сохраняет перевод в файле *_AutoGeneratedTranslations.txt*


## О файле с переводом

Файл содержит переводы для значительной части текста игры (более 30000 строк).

Тем не менее, некоторые фразы в игре содержат имена игроков, например:

> Your majesty, they stormed the castle of Lord Tykovka!
(Ваше величество, они осадили замок лорда Tykovka!)

или

> Your Greatness, I've no idea what Lord casualhoy is talking about. Maybe he's had too much wine, eh?
(Ваше величество, я понятия не имею, о чем говорит лорд casualhoy. Может, он выпил слишком много вина, а?)

Auto Translator не найдет такие фразы в файле и будет обращаться за переводом в Deepl или Google Translate во время игры.


## Установка

Существует уже два руководства по установке и настройке Auto Translator:

* [ES/FR/IT/RU INTERFACE LOCALIZATION FAN LOCALIZATION FOR ANY LANGUAGE](https://steamcommunity.com/sharedfiles/filedetails/?id=2943207189) от Ex-tier

* [Как же поиграть в King Of The Castle на Русском](https://steamcommunity.com/sharedfiles/filedetails/?id=2943164744) от Tykovka


### Вот перевод руководства от Ex-tier:

1. Скачайте программу [Auto Translator](https://github.com/bbepis/XUnity.AutoTranslator/releases/download/v5.2.0/XUnity.AutoTranslator-ReiPatcher-5.2.0.zip) и распакуйте содержимое архива в папку с игрой *(steamapps\common\King of the Castle)*

2. Скачайте [файл шрифта от Ex-tier](https://drive.google.com/file/d/1UXBkl-0yMqgnlW3gNR-fVJYsM57-Yg6o/view) и положите его также в папку с игрой

3. Запустите файл *SetupReiPatcherAndAutoTranslator.exe*

4. После установки запустите игру ярлыком *KingOfTheCastle (Patch and Run)*

5. При первом запуске программа создаст папку и файл настроек: *\AutoTranslator\Config.ini*

6. Закройте игру и откройте файл *Config.ini* в редакторе (блокноте)

7. Найдите указанные ниже строки с настройками и отредактируйте, чтобы они выглядели следующим образом (или скачайте и замените файл Config.ini):

```
Endpoint=DeepLTranslate
FallbackEndpoint=GoogleTranslateV2

Language=ru
FromLanguage=en

MaxCharactersPerTranslation=1000

OverrideFontTextMeshPro=Kotc_font_localization
```

8. Далее можно запускать игру обычным образом (через стим или ярлык на рабочем столе и т.д.)

9. Запустив игру, убедитесь что автоперевод на лету работает (нажмите комбинацию клавиш *Alt + 0* (ноль), чтобы отобразить панель плагина)

10. Закройте игру, скачайте файл с переводами и положите его в папку *steamapps\common\King of the Castle\AutoTranslator\Translation\ru\Text*

11. Можно играть


## Использование DeepL

Если вам нравится игра, но иногда плагин забывает перевести текст, это связано с тем, что в настройках мы используем бесплатный вариант сервиса DeepL с ограничениями.

В этом случае можно зарегистрировать бесплатный API аккаунт в DeepL на 500 тысяч слов/месяц - [DeepL API Free (для разработчиков)](https://www.deepl.com/ru/pro#developer). Аккаунт бесплатный, но требуется указать банковскую карту (не российскую) для подтверждения страны проживания. Либо зарегиструйте аккаунт другими способами.

После регистрации вы получите токен, который нужно указать в файле настроек. Итак, откройте файл *Config.ini*, найдите и отредактируйте следующие строки:

```
[Service]
Endpoint=DeepLTranslateLegitimate
FallbackEndpoint=GoogleTranslateV2

[DeepLLegitimate]
ExecutableLocation=
ApiKey=ЗАМЕНИТЕ НА ВАШ ТОКЕН DEEPL:fx
Free=True
```

Теперь перевод будет работать как надо.
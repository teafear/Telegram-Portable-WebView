 ## Установка и настройка Telegram для устранения ошибки "Error has crashed" для запуска приложений
  Это инструкция для тех как настроить Telegram чтобы он смог запускать мини приложения если обновления и переустановка telegram и webview вам не помогает. Будем работать c Telegram Portable Версией на примере диска C .
  ![Tgf](https://github.com/teafear/Telegram-Portable-WebView/blob/main/assets/Group%201.png)
## 1. Создание папки и скачивание необходимых файлов
  Создайте папку Telegram на диске C:
  Скачайте Telegram Portable и Microsoft Edge WebView2 (Fixed Version) для вашей архитектуры:
 - Перейдите по ссылке: https://telegram.org/dl/desktop/win64_portable
 - Перейдити по ссылке: https://developer.microsoft.com/en-us/microsoft-edge/webview2/
  <img src="https://github.com/teafear/Telegram-Portable-WebView/blob/main/assets/Group%202.png" width="200" />
    Выберите нужную архитектуру (x64, x86 или ARM64), примите соглашение и скачайте.

## 2. Распаковка файлов
### Распакуйте содержимое Telegram Portable в папку ```C:\Telegram```
После распаковки структура папок должна выглядеть следующим образом:
- C://
- ├── Telegram
- │   ├── Microsoft.WebView2.FixedVersionRuntime.-ВЕРСИЯ-.АРХИТЕКТУРА
- │   ├── Modules
- │   ├── Telegram.exe
### Вырежьте содержимое Microsoft.WebView2.FixedVersionRuntime.-ВЕРСИЯ-.АРХИТЕКТУРА и вставте в папку ```WebView2```
Теперь структура должна быть такой
- C://
- ├── Telegram
- │   ├── WebView2
- │   ├── Modules
- │   ├── Telegram.exe

## 3. Создание Ярлыка
### Создайте новый текстовый файл Telegram.txt в папке ```C:\Telegram```
### Откройте Telegram.txt и вставьте следующий код:
```bash
 set WEBVIEW2_BROWSER_EXECUTABLE_FOLDER=C:\Telegram\WebView2
 start Telegram.exe
```

Сохраните и переименуйте файл в ```Telegram.bat```
Теперь нажмите ПКМ по файлу ```Telegram.bat``` и создайте ярлык.

## 4. Настройка ярлыка
![Setup](https://github.com/teafear/Telegram-Portable-WebView/blob/main/assets/Group%203.png)
   
### Если вы хотите установить свой значок для ярлыка, нажмите ПКМ по ярлыку, выберите Свойства.
Перейдите в раздел Сменить значок, затем выберите Обзор.
Перейдите в папку ```C:\Telegram```, где находится файл ```Telegram.exe```, и выберите его.
## 5. Добавление в автозапуск

Нажмите Win + R и введите команду:
```bash
shell:startup
```
Откроется папка автозапуска. Скопируйте ваш ярлык и вставьте его в эту папку.

Теперь Telegram будет автоматически запускаться при старте системы. Чтобы отключить автозапуск, вы можете удалить ярлык из папки автозапуска или отключить программу в Диспетчере задач.

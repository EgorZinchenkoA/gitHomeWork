# Инструкция по Git
![Git-logo.png](Git-logo.png)
## Установка Git
 **Для windows**

 1. **Загрузите установщик Git**: Перейдите на официальный сайт Git.(https://git-scm.com/downloads) Затем автоматически будет загружен установщик Git для Windows.
 2. **Запустите установщик Git**: После загрузки установщика Git, найдите загруженный файл (обычно это файл формата .exe) и дважды щелкните по нему для запуска установщика.
 3. **Выберите параметры установки**: Установщик Git предложит несколько параметров настройки. Оставьте параметры по умолчанию или настройте их по своему усмотрению. Нажмите кнопку "Next" (Далее).
 4. **Проверка параметров установки**: Установщик Git проведет предварительную проверку параметров установки и покажет вам результаты. Убедитесь, что все параметры верны, и нажмите кнопку "Install" (Установить).
 5. **Завершение установки**: После завершения установки Git вы увидите окно с сообщением об успешной установке. Нажмите кнопку "Finish" (Готово), чтобы завершить установку.
 6. **Проверьте установку**: 
 Работу с ветками начинаем с запуска Git в репозитории. Вводим `git init` и `git status`, чтобы убедиться,что репозиторий создан.
Повторяем команды `git add`,`git log`, `git status`.
 
 **Для MacOS**

 1. **Загрузка установщика Git**:
 Перейдите на официальный сайт Git (https://git-scm.com/downloads) и загрузите установщик для macOS.
 2. **Запуск установщика**:
 После загрузки установщика Git, найдите загруженный файл (обычно это файл формата .dmg) и откройте его двойным щелчком. Это приведет к отображению окна установщика.
 3. **Установка Git**:
 В окне установщика перетащите иконку Git в папку "Applications". Это скопирует Git в папку "Applications" и завершит процесс установки.
 4. **Проверка установки**:
 Чтобы убедиться, что Git установлен правильно, откройте "Terminal" (можно найти в папке "Utilities" внутри папки "Applications") и выполните команду: `git --version`

 ## Настройка Git
 Вы установили себе Git и можете им пользоваться. Давайте теперь его настроим, чтобы когда вы создавали commit, указывался автор, кто его создал.
 Открываем терминал (Linux и MacOS) или консоль (Windows) и вводим следующие команды:

 * `git config --global user.name "<ваше_имя>"`
 * `git config --global user.email "<адрес_почты@email.com>"`

## Создание репозитория
Теперь вы готовы к работе с Git локально на компьютере.

Создадим наш первый репозиторий. Для этого пройдите в папку вашего проекта.
 Затем нужно написать команду для создания репозитрония.

 `git init` - *Инициализация/создание репозитория*

Теперь Git отслеживает изменения файлов вашего проекта. Но, так как вы только создали репозиторий в нем нет вашего кода. Для этого необходимо создать commit.
1. Добавим все файлы проекта в нам будующий commit с помощью одной из команд:
*  `git add .`
* `git add --all`

    Если хотим добавит конкретный файл, то можно так:
* `git add <имя_файла>`
2. Теперь создаем commit. Обязательно указываем комментарий.
* `git commit -m "<комментарий>"`

Отлично. Мы создали свой первый репозиторий и заполнили его первым commit.
## Ветки в Git
Под веткой принято понимать независимую последовательность коммитов в хронологическом порядке. Однако конкретно в Git реализация ветки выполнена как указатель на последний коммит в рассматриваемой ветке. После создания ветки уже новый указатель ссылается на текущий коммит.

Имя основной ветки Git-проекта по умолчанию — master (однако зачастую бывает main, например, в GitHub), она появляется сразу при инициализации репозитория. 

Команда `git branch` — главный инструмент для работы с ветвлением. С ее помощью можно добавлять новые ветки, перечислять и переименовывать существующие и удалять их.

Чтобы в Git добавить ветку мы используем:
* `git branch <branch_name>`

Если вы планируете переместиться на другую ветку, в том числе только что созданную, необходимо написать checkout:
* `git checkout <branch_name>`

 В Git предусмотрено слияние — перенос изменений с одной ветки на другую. Такие преобразования мы получаем, применив **git merge**:
 * `git merge <mergedBranch_name>`
## Базовые команды
Для работы в репозитории следуюет овладлеть следующими командами:
* `git init` - инициализация локального репозитория
* `git status` - получить информацию от git о его текущем состоянии
* `git add` - добавить файл или файлы к следующему коммиту
* `git commit -m "ваш комментарий"` - создание коммита
* `git log` - вывод на экран истории всех коммитов с их хеш - кодами
* `git diff <целевая_ветка>` - увидеть разницу между текущим файлом и закоммиченным файлом
* `git checkout` - переход от одного коммита к другому
* `git checkout master`  - вернуться к актуальному состоянию и продолжить работу
## Какие проблемы могут возникнуть?
Git старается автоматически сливать изменения, однако это не всегда возможно. Иногда возникают конфликты. Например, когда в двух ветках были изменения в одной и той же строчке кода. Если такое произошло, то необходимо разрешить конфликт вручную. Пример вы можете увидеть на данном скриншоте:
![Conflict.png](Conflict.png)
Для любого конфликта существует несколько путей решения, которые расположены над конфликтом:
* _Принять текущее изменение_ - Нажимая эту кнопку мы сохраняем то изменение, которое было в ветке, **в которой** мы провели слияние.
* _Принять входящее изменение_ - Нажимая эту кнопку мы сохраняем то изменение, которое было в ветке, __с которой__ мы провели слияние. То есть название этой ветки использовалась в команде `git merge <branch name>`.
* _Принять оба изменения_ - Данная команда сохраняет оба изменения в текущей ветке.

Над конфликтом так же будет кнопка **Сравнить изменения**. Нажав эту кнопку, мы получим сравнение двух версий, чтобы в последствие мы могли выбрать, какое из действий нам совершить по отношению к конфликту. Пример сравнения вы можете увидеть на скриншоте снизу:
![Compare.png](Compare.png)


## Итог
В данной работе мы написали основную информацию по работе с Git для новичков.
Из того, что есть в данной работе, можно выделить:
* Как устанавливать Git
* Как настраивать Git
* Как инициализировать репозиторий и создать commit через консоль
* Как создавать новые ветки, сливать и удалять их
* Рассказали о том, что такое конфликты, как они возникают и как их решить

# На этом все, спасибо! 
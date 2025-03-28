##                                                                               Навигация

• pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;

• ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;

• ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;

• cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;

• cd first-project/html — перейди в папку html, которая находится в папке first-project;

• cd .. — перейди на уровень выше, в родительскую папку;

• cd ~ — перейди в домашнюю директорию (/Users/Username);

• cd / — перейди в корневую директорию.

##                                                                        Работа с файлами и папками
##                                                                                Создание

• touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;

• touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;

• mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.

##                                                                        Копирование и перемещение

• cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;

• mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.

##                                                                                   Чтение

• cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.

##                                                                                   Удаление

• rm about.html (от англ. remove, «удалить») — удали файл about.html;

• rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;

• rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.

##                                                                             Полезные возможности

• Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).

• У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).

• Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама. 
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter. 

Терминал — мощный инструмент с практически бесконечным количеством команд и параметров. Не переживайте, если не можете запомнить их все. Использовать поисковики или заглядывать в шпаргалку — абсолютно нормально. Даже разработчики с большим опытом часто обращаются к интернету, чтобы что-то вспомнить. В следующей теме продолжим погружение в мир Git!


'''mermaid
graph LR;
    Git --> "Работа с файлами и папками";
    "Работа с файлами и папками" --> "Создание";
    "Работа с файлами и папками" --> "Копирование и перемещение";
    "Работа с файлами и папками" --> "Чтение";
    "Работа с файлами и папками" --> "Удаление";
    "Работа с файлами и папками" --> "Полезные возможности";
'''

##                                                                    Команда git commit выведет информацию о коммите.

• [master (root-commit) baa3b6e] значит: 

o коммит был в ветке master;

o root-commit — это самый первый, или «корневой» (англ. root), коммит в ветке, у следующих коммитов такой надписи не будет;

o baa3b6e — сокращённый идентификатор коммита (подробнее об этом мы ещё расскажем).

• 2 files changed, 1 insertion(+) значит: 

o изменились два файла (readme.txt и todo.txt);

o одна строка была добавлена (1. Пройти пару уроков по Git.).

• Строки вида create mode 100644 readme.txt — это более подробная информация о новых (добавленных в Git) файлах. 

o create (англ. «создать») говорит, что файл был создан. Если бы файл был удалён, на этом месте было бы слово delete (англ. «удалить»).

o mode 100644 сообщает, что это обычный файл. Также возможны варианты 100755 для исполняемых файлов (например, что-нибудь.exe) и 120000 для файлов-ссылок в Linux. Файлы-ссылки не содержат данных сами по себе, а только ссылаются на другие файлы — как «ярлыки» в Windows.

##                                                                                Зачем вообще писать сообщения 

• У каждого коммита в Git есть сообщение — то, что передаётся после параметра -m. Например: git commit -m "Добавить урок про оформление сообщений коммитов".
• Как и надпись на коробке, сообщение коммита должно помочь определить, что внутри.
• Есть общие рекомендации по тому, как правильно составить сообщение. Оно должно быть:
o относительно коротким, чтобы его было легко прочитать;
o нформативным.
• Пример полезного сообщения в репозитории новостного сайта: Исправление опечатки в заголовке главной страницы на английском

##                                                                                      Стили оформления         

Примеры формулирования сообщений коммитов:

• инфинитивы: Исправить сообщение об ошибке E123
• глаголы в прошедшем времени: Исправил…
• существительные: Исправление…

Без единообразия коммитов нет и эффективной работы в Git. Это может показаться мелочью, но когда коммиты с сообщениями в разных стилях идут друг за другом, их может быть сложно читать.

Чтобы упростить работу, команды или даже целые компании часто договариваются об определённом стиле (то есть о правилах) оформления сообщений коммитов:

• длина сообщения от 30 до 72 символов;
• первое слово — глагол в инфинитиве («исправить», «дополнить», «добавить» и другие);
• и так далее.

##                                                                                          Корпоративный стиль

Jira — система для организации проектов и задач.

У каждой задачи в Jira есть идентификатор из нескольких заглавных латинских букв и номера. Например, LGS-239 значит, что это 239-я задача в проекте LGS (сокращение от англ. logistics — «логистика»).
В корпоративном стиле в начале сообщения обычно указывают Jira-ID, а после — текст сообщения:

$ git commit -m "LGS-239: Дополнить список пасхалок новыми числами" 

##                                                                                    Стандарт Conventional Commits

Отличается качественной документацией и подробной проработкой. Он подходит для репозиториев с исходным кодом программ. А вот использовать его для других типов проектов было бы неудобно.

Conventional Commits предлагает такой формат коммита: <type>: <сообщение>. 
Первая часть type — это тип изменений. Таких типов достаточно много. 

Вот два примера:

feat (сокращение от англ. feature) — для новой функциональности;

fix (от англ. «исправить», «устранить») — для исправленных ошибок.

Например, сообщение может быть таким.

git commit -m "feat: добавить подсчёт суммы заказов за неделю" 

##                                                                                              GitHub-стиль

GitHub можно использовать не только для хранения файлов проекта, но и для ведения списка задач (англ. issue) этого проекта. Если коммит «закрывает» или «решает» какую-то задачу, то в его сообщении удобно указывать ссылку на неё. Для этого в любом месте сообщения нужно указать #<номер задачи>. Например, вот так.

$ git commit -m "Исправить #334, добавить график температуры" 
В таком случае GitHub свяжет коммит и задачу.
💡 Для сообщений на русском языке часто рекомендуют использовать инфинитивы. Например: Добавить тесты для PipkaService, Исправить ошибку #123 и так далее.
Для сообщений на английском рекомендуется использовать повелительное наклонение (англ. imperative). Например: Use library mega_lib_300, Fix exit button и так далее.
Эти рекомендации сложились исторически, и им следуют многие проекты.

##                                                                                        Хеш — идентификатор коммита

Хеширование — это способ преобразовать набор данных и получить их «отпечаток».

Git хеширует (преобразует) содержимое файлов в репозитории на момент коммита и ссылкe на предыдущий с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») 
и получает для каждого коммита свой уникальный хеш — результат хеширования - символьная строка. Она относительно коротка (40 символов в случае SHA-1) и состоит из цифр 0—9 и латинских букв A—F
(неважно, заглавных или строчных). Хеш обладает следующими важными свойствами:

• если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;

• если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится (причём сильно). 

Git хранит таблицу соответствий хеш → информация о коммите. Если вы знаете хеш, вы можете узнать всё остальное: автора и дату коммита и содержимое закоммиченных файлов.

##                                                                                            HEAD — всему голова

Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).
Внутри HEAD — ссылка на служебный файл: refs/heads/master (или refs/heads/main в зависимости от названия ветки). Если заглянуть в этот файл, можно увидеть хеш последнего коммита.

##                                                                                            Как исправить коммит

в только что выполненном коммите нужно что-то поменять - можно внести правки в уже сделанный коммит с помощью опции --amend (от англ. amend — «исправить», «дополнить») у команды commit: git commit --amend.

Дополнить коммит новыми файлами — git commit --amend --no-edit:
Дополните последний коммит забытым файлом common.css с помощью опции --amend.

$ git add common.css

добавили файл common.css в список на коммит как обычно

но вместо команды commit -m '...' будет:

$ git commit --amend --no-edit

$ git log --oneline

8340eb2 Добавить главную страницу

коммит в истории всё ещё один (но у него новый хеш) 
С опцией --amend команда commit создаст новый коммит, которым заменит ваш последний. При этом будут учтены изменения как старого коммита, так и нового.

Обратите внимание на опцию --no-edit. Она сообщает команде commit, что сообщение коммита нужно оставить как было.

Точно так же можно добавить не новый файл, а дополнительные изменения в уже добавленном в коммит файле.

ещё раз отредактировали main.html

$ git add main.html # добавили в список на коммит
$ git commit --amend --no-edit 

##                                                                      Изменить сообщение коммита — git commit --amend -m "Новое сообщение" 

Может быть и так, что добавлять новые файлы в коммит не нужно, зато понадобилось изменить сообщение. Допустим, хочется заменить сообщение Добавить главную страницу на Добавить главную страницу и стили. Сделать это можно через commit --amend с флагом -m.

$ git commit --amend -m "Добавить главную страницу и стили"
$ git log --oneline
a31fa24 Добавить главную страницу и стили 

##                                                                                     Как откатиться назад, если «всё сломалось»

Допустим, вы создали или изменили какой-то файл и добавили его в список «на коммит» (staging area) с помощью git add, но потом передумали включать его туда. Убрать файл из staging поможет команда git restore --staged <file> (от англ. restore — «восстановить»).
💡 В выводе команды git status есть подсказка в скобках: use "git restore --staged <file>..." to unstage. Так что, даже если вы и забыли эту команду, Git напомнит вам.
В терминале это будет выглядеть примерно так.

$ touch example.txt # создали ненужный файл
$ git add example.txt # добавили его в staged

$ git status # проверили статус
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   example.txt

$ git restore --staged example.txt
$ git status # проверили статус

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        example.txt

no changes added to commit (use "git add" and/or "git commit -a")

файл example.txt из staged вернулся обратно в untracked 

Чтобы «сбросить» все файлы из staged обратно в untracked/modified, можно воспользоваться командой git restore --staged .: она сбросит всю текущую папку (.).

##                                                                                   «Откатить» коммит — git reset --hard <commit hash>

Откатить то, что уже было закоммичено, то есть вернуть состояние репозитория к более раннему - git reset --hard <commit hash>:

$ git log --oneline # хеш можно найти в истории
7b972f5 (HEAD -> master) style: добавить комментарии, расставить отступы
b576d89 feat: добавить массив Expenses и цикл для добавления трат # вот сюда и вернёмся
4b58962 refactor: разделить analyzeExpenses() на countSum() и saveExpenses()

$ git reset --hard b576d89

Теперь коммит b576d89 стал последним: вся дальнейшая разработка будет вестись от него. Файл также вернулся к тому состоянию, в котором был в момент этого коммита.А коммит 7b972f5 Git просто удалил.
HEAD is now at b576d89 feat: добавить массив Expenses и цикл для добавления трат 

$ git log --oneline
b576d89 (HEAD -> master) feat: добавить массив Expenses и цикл для добавления трат
4b58962 refactor: разделить analyzeExpenses() на countSum() и saveExpenses() 

##                                                               «Откатить» изменения, которые не попали ни в staging, ни в коммит, — git restore <file>

Может быть так, что вы случайно изменили файл, который не планировали. Теперь он отображается в Changes not staged for commit (modified). Чтобы вернуть всё «как было», можно выполнить команду git restore <file>.

# случайно изменили файл example.txt
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
          modified:   example.txt

$ git restore example.txt
$ git status
On branch main
nothing to commit, working tree clean 
Изменения в файле «откатятся» до последней версии, которая была сохранена через git commit или git add.










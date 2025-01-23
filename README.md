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

##
                                                                                   Чтение
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



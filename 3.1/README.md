8. Ознакомиться с разделами man bash, почитать о настройках самого bash:
 * HISTSIZE строка 1309 <br />
 * Значение ignoreboth объединяет в себе сразу 2 значения: ignorespace — игнорирует сохранение строк начинающихся с пробела, </b>
ignoredups — заставляет игнорировать дубликаты </b>
предыдущих записей, значение erasedups перед сохранением удаляет все предыдущие команды из истории соответствующие данной команде.<br />

9.В каких сценариях использования применимы скобки {} и на какой строчке man bash это описано? <br />
* {} - зарезервированные слова, список, в т.ч. список команд команд в отличии от "(...)" исполнятся в текущем инстансе, 
 используется в различных условных циклах, условных операторах, или ограничивает тело функции, 
 В командах выполняет подстановку элементов из списка , если упрощенно то  цикличное выполнение команд с подстановкой 
 например mkdir ./DIR_{A..Z} - создаст каталоги сименами DIR_A, DIR_B и т.д. до DIR_Z
 строка 343<br />
 
10.С учётом ответа на предыдущий вопрос, как создать однократным вызовом touch 100000 файлов? Получится ли аналогичным образом создать 300000? Если нет, то почему?<br />
* touch {000001..100000}.txt 
* 300000 - создать не получится, слишком дилинный список аргументов, максимальное число - 110188

11.В man bash поищите по /\[\[. Что делает конструкция [[ -d /tmp ]] 
* проверяет условие у -d /tmp и возвращает ее статус (0 или 1), наличие катаолга /tmp <br />

12. Основываясь на знаниях о просмотре текущих (например, PATH) и установке новых переменных; командах, которые мы рассматривали, 
добейтесь в выводе type -a bash в виртуальной машине наличия первым пунктом в списке:<br />

mkdir /tmp/new_path_dir/ <br />
cp /bin/bash /tmp/new_path_dir/ <br />
type -a bash <br />
bash is /usr/bin/bash <br />
bash is /bin/bash <br />
PATH=/tmp/new_path_dir/:$PATH <br />
type -a bash <br />
bash is /tmp/new_path_dir/bash <br />
bash is /usr/bin/bash <br />
bash is /bin/bash <br />

13.Чем отличается планирование команд с помощью batch и at?
* at - команда запускается в указанное время (в параметре)
* batch - запускается когда уровень загрузки системы снизится ниже 1.5.<br />
   
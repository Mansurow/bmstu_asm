# Лабораторная работа 2 "Создание простейших программ на ассамблер. Отладчик."

Все EXE файлы и DosBox в - https://drive.google.com/drive/folders/15d5tq85jYTIIs9tT2a_5l_w2ysexK2VZ

## Процесс

Выполняется практическое задание:

- 1 - Создать hello.asm и поместить туда программу (разбираться в коде не надо)
   
Примечание: С каждым годом, немного меняется реализация программы (лучше взять из файлов преподавателя)

- 2 - Запустить DosBox указать путь с помощью команд:
```
mount c /YOUR_PATH/
C: - перейти в диск где находится ваш проект.
```

- 3 - Склмпилировать программу

```
ML.EXE /AT HELLO.ASM
```

- 4 - Посмотреть что находится в исполняемом и объектном файле (использовается HexView, например, в Visual Studio)

- 5 - Запустить отладчик программы, с помощью:

```
AFDPRO.EXE HELLO.COM
```

- 6 - Разобраться что и где располагается.

![image](https://user-images.githubusercontent.com/62243773/156164918-35b7e1c5-81fe-4f9c-90ed-83882b609e6c.png)

## Вопросы

- 1 - Что находится в исполняемом файле и что именно отображается через HexView?

В исполняемом файле находится набор данных, 

![image](https://user-images.githubusercontent.com/62243773/156164683-bb1ce7ca-2945-4bdc-b749-fe9ea77abb2c.png)

` 00000010 ` - смещение по ячейкам данных

Данные распалагаются в 16 системе счисления

- 2 - Что вот это за окно в отладчике:

![image](https://user-images.githubusercontent.com/62243773/156164958-c1721fa2-52ef-475a-b87a-8480d0182774.png)

Это регистры для работы в программе.

![image](https://user-images.githubusercontent.com/62243773/156165186-ee08fce2-b719-4309-ae03-1594395fce32.png)

Это стек и флажки

![image](https://user-images.githubusercontent.com/62243773/156165326-4d0bce54-3355-4809-93e3-8a7aebd83d47.png)

Это окно кода программы 

`0100` - смещение по коды, на который указывает указатель IP, в случае если следующая команда будет выполнятся она.

`B409` - набор данных, по которым выполняется программа

![image](https://user-images.githubusercontent.com/62243773/156165628-9df39f06-85a1-45aa-bd39-10511ba192dc.png)

Это сегмент данных.

- 3 - Что такое регистр?

Регистры процессора — блок ячеек памяти, образующий сверхбыструю оперативную
память внутри процессора. Большинство команд процессора манипулируют данными,
хранящимися в регистрах

- 4 - Что такое регистры общего назначения и где они показана в отладчике?

![image](https://user-images.githubusercontent.com/62243773/156165761-32ab5e2d-5200-4bb7-9127-6d4204e050e5.png)

Регистры общего назначения процессора (РОН) 8086. Регистры общего назначения - группа регистров, доступная для чтения/записи основными командами.
Предназначены для временного хранения данных, записи параметров машинных
команд, арифметической обработки и т.д. Существует всего 4 РОН: AX, BX, CX, DX.
Каждый содержит в себе 16 бит и делится на 2 части по 8 бит - старшую (high, H) и
младшую (low, L). Обращаться можно как к регистру целиком, так и к его половинам по
отдельности.

![image](https://user-images.githubusercontent.com/62243773/156165839-3d568775-2234-48cb-9edc-f4686a253afd.png)

- 5 - Что такое IP?

![image](https://user-images.githubusercontent.com/62243773/156165968-2bd96284-1f3e-4201-83b6-b97793ae8b19.png)

Регистр указателя команд (IP, Instruction pointer) - специальный регистр, который
всегда хранит в себе смещение команды, которая будет выполнена следующей.
Меняется автоматически по ходу выполнения программы и не может быть изменён
программно.

- 6 - Где хранятся сегмент данных?

DS - это сегмент данных, который хранится во внутренней памяти компьютора в ОЗУ (оперативной памяти), так это необходимо для быстрой связи с данными во время выполнения программы.

- 7 - Перечислите виды памяти ЭВМ?

Внутренная память (ОЗУ и ПЗУ)
Внешняя память (жесткий диск и флэшка)
Центральный процессор (Нужен для хранения регистра)

- 8 - Для чего нужна ПЗУ?

ПЗУ в основном нужна для чтения данных и хранения независимых данных.





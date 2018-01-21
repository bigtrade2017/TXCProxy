# Сборка
TXCProxy разрабатывался с использованием компилятора и инструментов входящих в 
состав проекта [Open Watcom](http://www.openwatcom.org/). При настроенной среде, 
сборка осуществляется простым запуском команды wmake в каталоге с распакованными 
исходными текстами, в результате должен появиться исполняемый файл txcproxy.exe

### Visual C++

    cl *.c ws2_32.lib /link /out:txcproxy.exe

### MinGW   
    
    gcc -o txcproxy.exe *.c -lws2_32
    
# Установка
Установка заключается в создании произвольного каталога и копирование в него файла 
txcproxy.exe и библиотеки [txmlconnector.dll](http://www.finam.ru/howtotrade/tconnector/default.asp)

# Запуск
Строка запуск на платформе Windows будет иметь следующий вид:

    txcproxy.exe -tq_addr -tq_port [-px_addr -px_port [options]]

На платформах *NIX под [wine](http://www.winehq.org):

    WINEDEBUG=-all wine txcproxy.exe -tq_addr -tq_port [-px_addr -px_port [options]]
    
TXCProxy принимает следующие параметры (tq_addr и tq_port являются обязательными):
    
    | Параметр | Описание                             | Значение по умолчанию 
    -------------------------------------------------------------------------
    | addr     | IP адрес входящих подключений        | ANY 
    | port     | номер порта входящих подключений     | 4444 
    | tq_addr  | IP адрес сервера TRANSAQ             | - 
    | tq_port  | номер порта TRANSAQ                  | - 
    | px_type  | тип прокси                           | - 
    | px_addr  | IP адрес прокси сервера              | - 
    | px_port  | номер порта прокси сервера           | - 
    | px_user  | имя пользователя для прокси          | - 
    | px_pass  | пароль для прокси                    | - 
    | dll      | путь к библиотеке коннектора         |.\txmlconnector.dll 
    | ll2      | уровень детализации логов коннектора | 0 

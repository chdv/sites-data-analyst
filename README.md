# Аналитика данных с сайтов
Программа позволяет сохранять содержимое определенных страниц выбранного сайта (игнорируя пейджинг и прочие лишние данные) и вести архив данной информации.
В потенциале будет реализована аналитика получаемых данных.

В настоящий момент реализовано сохранение данных с сайта hh.ru и rabota.yandex.ru по поисковым запросам. Ключевые слова указываются в конфигурационном файле analyst-config.xml.
Результат выполнения сохраняется в наборе файлов. Запросы к сайтам и наименование создаваемых файлов выводятся в лог.

Особенностью архитектуры является реализация параллельного доступа к сайтам по каждому ключевому запросу, асинхронная запись получаемой информации в файлы.
То есть данные перед сохранением не помещаются ни в какие буфера (что могло бы способствовать созданию менее связной архитектуры), в итоге экономится память, увеличивается быстродействие.
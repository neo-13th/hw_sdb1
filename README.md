# homework_sdb1
## Задание 1. СУБД
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Приведите ответ в свободной форме.   
### Ответ

1.1 Для данного типа задач можно рассмотреть использование реляционных СУБД, так как  они поддерживают SQL-запросы, что позволяет удобно анализировать и формировать отчеты. Из основных популярных реляционных СУБД можно использовать следующие: PostgeSQL, MySQL, Microsoft SQL Server.  
  
1.2 Для лендингов и CRM лучше всего использовать реляционные СУБД, такие как MySQL или PostgreSQL. Они обладают гибкостью и обеспечивают высокую скорость работы с данными.

1.3 Для создания базы данных, которая будет соответствовать требованиям, можно выбрать реляционные системы управления базами данных, такие как MySQL или PostgreSQL. Эти решения имеют простой и понятный интерфейс, позволяющий легко создавать базы данных с нужной структурой. Они обладают высокой производительностью и надежностью, что важно для хранения корпоративных данных. Также можно реализовать на NoSQL СУБД, если хранить данные не ввиде таблиц, а в виде документов. 

1.4 Для решения этих задач можно использовать СУБД, такую как PostgreSQL или Oracle. Эти СУБД позволяют быстро работать со сложными связями между объектами и эффективно распределять ресурсы. Можно подключить отдел закупок к СУБД PostgreSQL или Oracle. Обе эти СУБД предоставляют широкие возможности для создания и управления базами данных, которые могут быть использованы в разных отделах компании, включая отдел закупок.

## Задание 2. Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Приведите ответ в свободной форме.  
### Ответ
1. Пользователь вводит номер  телефона и сумму пополнения в мобильном приложении.  
2. Данные отправляются оператору, где происходит проверка доступности средств.  
3. Если средства доступны,  отправляется запрос на подтверждение транзакции на телефон .  
4. Пользователь подтверждает списание средств, введя специальный код, отправленный оператором.  
5. Оператор списывает сумму пополнения со счета пользователя и кладет ее на баланс телефона.  
6. Баланс на  телефонном номере обновляется.



## Задание 3. SQL vs NoSQL
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Приведите ответ в свободной форме.  
### Ответ
1. Высокий уровень безопасности  
2. Большой выбор библиотек и программных иснтрументов
3. Структурированность: данные хранятся в таблицах с явно определёнными связями и ограничениями
4. Поддержка ACID
5. Маштабируемость.SQL-базы данных могут масштабироваться и поддерживать большие объёмы данных.

## Задание 4. Кластеры
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

Приведите ответ в свободной форме.  
### Ответ
1. Горизонтальная масштабируемость. Поскольку данных может быть сколь угодно много – любая система, которая подразумевает обработку больших данных, должна быть расширяемой. В 2 раза вырос объём данных – в 2 раза увеличили количество железа в кластере и всё продолжило работать.
2. Отказоустойчивость. Принцип горизонтальной масштабируемости подразумевает, что машин в кластере может быть много. Например, Hadoop-кластер Yahoo имеет более 42000 машин (по этой ссылке можно посмотреть размеры кластера в разных организациях). Это означает, что часть этих машин будет гарантированно выходить из строя. Методы работы с большими данными должны учитывать возможность таких сбоев и переживать их без каких-либо значимых последствий.
3. Локальность данных. В больших распределённых системах данные распределены по большому количеству машин. Если данные физически находятся на одном сервере, а обрабатываются на другом – расходы на передачу данных могут превысить расходы на саму обработку. Поэтому одним из важнейших принципов проектирования BigData-решений является принцип локальности данных – по возможности обрабатываем данные на той же машине, на которой их храним.
   
Для этих задач применяют особое ПО, которое работает по технологии MapReduce.  
Сначала алгоритм отбирает данные по заданным параметрам, затем распределяет между отдельными узлами, серверами или компьютерами, а потом они одновременно обрабатывают эти сегменты данных, параллельно друг с другом.  
Из инструментов можно выделить:  

Apache Hadoop. Включает в себя распределенную файловую систему HDFS и фреймворк для обработки данных MapReduce. 

Apache Spark. Фреймворк для параллельной обработки данных, который предоставляет API на Java, Scala, Python и R. Spark поддерживает обработку данных в реальном времени и в памяти, что делает его более быстрым по сравнению с Hadoop MapReduce.  

NoSQL-базы данных. Такие как Apache Cassandra, MongoDB и Couchbase, предоставляют масштабируемые и гибкие решения для хранения и обработки неструктурированных данных, что особенно важно для Big Data-приложений. 



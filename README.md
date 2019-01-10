# Управление миграциями БД с Liquibase

Система миграций схемы базы данных Liquibase хороша тем, что позволяет использовать системы контроля версий, VCS, (например, Git) для управления ревизиями базы данных приложения. Говоря более точно, VCS содержит описание изменений, необходимые для миграции схемы базы данных из одной ревизии в другую.

Кроме схемы и операций DDL, Liquibase позволяет мигрировать данные приложения, с поддержкой наката изменений данных и их отката. 


Liquibase использует так называемые «чейнджсеты» (changeset — набор изменений), XML-код для описания операторов DDL. Они составляют файлы чейнджлогов (changelog). Следующий чейнджсет создаст таблицу (тэг «createTable») и два столбца (тэг «column»).

    <databasechangelog xmlns="http://www.liquibase.org/xml/ns/dbchangelog" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemalocation="http://www.liquibase.org/xml/ns/dbchangelog http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-2.0.xsd">
      <changeset id="1" author="mueller@synyx.de" runonchange="true"> 
        <createtable tablename="Person"> 
          <column autoincrement="true" name="id" type="BIGINT"> 
            <constraints nullable="false" primarykey="true"> 
            </constraints>
          </column> 
          <column name="name" type="VARCHAR(255)"> 
            <constraints nullable="false"> 
            </constraints>
          </column> 
        </createtable> 
      </changeset>
    </databasechangelog>
    
    
 Liquibase также хорошо интегрируется с Maven (как goal) или Spring (как бин, запускаемый во время инициализации контекста).
 Liquibase имеет встроенную поддержку отката некоторых типов чейнджсетов, к примеру «createTable». Если мы вызовем Liquibase   через командную строку с аргументом «rollbackCount 1» вместо «update», произойдет откат последнего чейнджсета: таблица PERSON будет удалена.
 
 
 # Vue 
 # Используем Axios для доступа к API
 
 При создании веб-приложения вам может понадобиться получать и отображать данные из API. Существует несколько способов сделать это, но наиболее популярным решением является использование axios, основанного на промисах HTTP-клиента.
 
 #FileSaver
 
 FileSaver.js является решением для сохранения файлов на стороне клиента и идеально подходит для веб-приложений, которые генерируют файлы на клиенте.
 
 #Moment.js
 
 Moment.js это отличная библиотека для работы с датами в JavaScript. Примеры под катом.


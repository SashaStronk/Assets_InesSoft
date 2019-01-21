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
 
 # FileSaver
 
 FileSaver.js является решением для сохранения файлов на стороне клиента и идеально подходит для веб-приложений, которые генерируют файлы на клиенте.
 
 # Moment.js
 
 Moment.js это отличная библиотека для работы с датами в JavaScript. Примеры под катом.
 
 # Vue Router — официальная библиотека маршрутизации для Vue.js. Она глубоко интегрируется с Vue.js и позволяет легко создавать SPA-приложения. Включает следующие возможности:

Вложенные маршруты/представления
Модульная конфигурация маршрутизатора
Доступ к параметрам маршрута, query, wildcards
Анимация переходов представлений на основе Vue.js
Удобный контроль навигации
Автоматическое проставление активного CSS класса для ссылок
Режимы работы HTML5 history или хэш, с авто-переключением в IE9
Настраиваемое поведение прокрутки страницы

# Vuex

Vuex — паттерн управления состоянием + библиотека для приложений на Vue.js. Он служит централизованным хранилищем данных для всех компонентов приложения с правилами, гарантирующими, что состояние может быть изменено только предсказуемым образом. Vuex интегрируется с официальным расширением vue-devtools, предоставляя «из коробки» такие продвинутые возможности, как «машину времени» для отладки и экспорт/импорт слепков состояния данных.

Это самостоятельное приложение состоит из следующих частей:

 - Состояние — «источник истины», управляющий приложением;
 - Представление — отображение состояния заданное декларативно;
 - Действия — возможные пути изменения состояния приложения в ответ на
   взаимодействие пользователя с представлением.
   
   # Vuetify
   
   Библиотека Vuetify даёт разработчикам возможности по созданию пользовательских интерфейсов с использованием принципов Google Material Design.


# Constructor-based dependency injection

Constructor-based DI is accomplished by the container invoking a constructor with a number of arguments, each representing a dependency. Calling a static factory method with specific arguments to construct the bean is nearly equivalent, and this discussion treats arguments to a constructor and to a static factory method similarly. The following example shows a class that can only be dependency-injected with constructor injection. Notice that there is nothing special about this class, it is a POJO that has no dependencies on container specific interfaces, base classes or annotations.

    public class SimpleMovieLister {
    
        // the SimpleMovieLister has a dependency on a MovieFinder
        private MovieFinder movieFinder;
    
        // a constructor so that the Spring container can inject a MovieFinder
        public SimpleMovieLister(MovieFinder movieFinder) {
            this.movieFinder = movieFinder;
        }
        // business logic that actually uses the injected MovieFinder is omitted...
    }

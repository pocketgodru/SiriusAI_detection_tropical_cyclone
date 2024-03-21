# **Детекция тропических циклонов**

## Содержание:
  
- [🌪Введение](#введение)

- [🌟Актуальность](#актуальность)

- [📌Цель и задачи](#цель-и-задачи)

- [👤Целевая аудитория](#целевая-аудитория)

- [🔍Анализ области](#анализ-области)

- [📋Функциональные и нефункциональные требования](#функциональные-и-нефункциональные-требования)

- [❕Общие и локальные ограничения](#общие-и-локальные-ограничения)

- [🌐Технологическая основа](#технологическая-основа)

- [📚Подготовка датасета](#подготовка-датасета)

- [🤖Обучение модели](#обучение-модели)

- [🔃Схема взаимодействия с моделью](#схема-взаимодействия-с-моделью)

- [🎨Интерфейс пользователя](#интерфейс-пользователя)

- [🔜Совершенствование проекта](#совершенствование-проекта)

- [📩Обратная связь](#обратная-связь)

# 🌪Введение
Проект направлен на распознавание тропических циклонов путем обучения модели и предоставление спутникового изображения. Обнаружение тропических циклонов важно для безопасности людей и экономики стран. Проект должен обеспечивать предупреждение и обнаружение циклонов и тем самым предотвращать человеческие жертвы, минимизировать разрушения и защищать экосистему.

Объектом исследования проекта является система для распознавания тропических циклонов с использованием спутниковых снимков. Предмет исследования включает использование метода YOLO (You  Only  Look  Once) для обучения нейронной сети, способной точно и быстро идентифицировать тропические циклоны на спутниковых изображениях, а также создание графического интерфейса для удобства пользователей. Этот подход позволяет повысить эффективность системы предупреждения о стихийных бедствиях.

# 🌟Актуальность
Обнаружение тропических циклонов представляет собой важную деятельность в современной метеорологии, привлекая внимание исследователей и специалистов в различных странах, особенно в регионах, где эти природные явления являются распространёнными и опасными.

Медленная реакция на стихийные бедствия может привести к большему числу пострадавших и ухудшить ситуацию в затронутых районах. Если предупреждения и координация действий работают не так, как нужно, то остаётся меньше времени для подготовки и эвакуации.

***Решение должно обеспечивать следующие сценарии:***
-   Предупреждение о чрезвычайных ситуациях
-   Сокращение ущерба и потерь
-   Исследования климатических изменений

***Статистические данные о тропических циклонах за последние 50 лет подчёркивают их серьёзное воздействие:***
-   1,945 стихийных бедствий
-   Более 779,324 унесённых жизней
-   Экономические потери в размере $1.4 трлн
-   Процентная доля населения регионов, подверженных тропическим циклонам, увеличилась на 200%

Эти данные подчёркивают необходимость эффективного управления рисками и разработки стратегий предупреждения.

***Важность этой проблемы проявляется в нескольких ключевых аспектах:***

 - Предотвращение человеческих жертв 
 - Минимизация разрушений
 - Инфраструктура и сохранение экосистем
 
Отслеживание тропических циклонов играет решающую роль в снижении потерь людских жизней и содействии безопасности общества.

Дополнительно, управление рисками, связанными с тропическими циклонами, способствует защите экономики. Эти природные явления оказывают значительное воздействие на экономику стран и регионов, где развито сельское хозяйство, туризм и прочие виды деятельности. Оперативное обнаружение и мониторинг циклонов позволяют более эффективно планировать и принимать меры для защиты инфраструктуры.

С точки зрения научных исследований, понимание и прогнозирование тропических циклонов играют ключевую роль в изучении климатических изменений. Это необходимо для разработки более точных моделей и улучшения наших знаний.
 
# 📌Цель и задачи
**Цель** данного проекта – создание системы, которая сможет обеспечивать оперативное предупреждение и обнаружение тропических циклонов для минимизации потерь и разрушений.

**Задачи:**
-   Анализ существующих решений
-   Выбор наиболее подходящего семейства нейронных сетей
-   Создание или поиск датасета с нужными нам данными
-   Обучение модели для обнаружения расположения циклона, его центра
-   Тестирование модели
-   Создание графического интерфейса

В результате должна получиться программа, способная достаточно точно определять тропический циклон и его центр на спутниковых снимках.

Также важно создание графического интерфейса для более удобного взаимодействия с пользователями.

# 👤Целевая аудитория
В целевую аудиторию данного проекта входят разнообразные группы, включая местных жителей, органы власти, службы экстренного реагирования и гражданскую инфраструктуру.

***Несколько ключевых групп, которые могут быть заинтересованы в таком проекте:***

-   **Местные жители**
Люди, проживающие в регионах, где тропические циклоны представляют угрозу. Этой группе нужна надёжная система предупреждения для защиты своей жизни и имущества от стихийных бедствий.

-   **Власти и службы экстренного реагирования**
Государственные и местные органы, а также службы экстренного реагирования, ответственные за организацию эвакуаций и координацию усилий по восстановлению инфраструктуры после катастроф.

-   **Гражданская инфраструктура (школы, больницы, дороги)**
Организации и учреждения, такие как школы и больницы, а также инфраструктурные объекты, находящиеся в рискованных регионах, нуждаются в защите от негативных последствий тропических циклонов для обеспечения стабильной работы.

# 🔍Анализ области

В ходе исследования в области систем детекции тропических циклонов были выявлены аналоги проекта.

### 1. Актуальное решение проблемы краткосрочного прогноза тропических циклонов
В настоящее время в Дальневосточном научно-исследовательском гидрометеорологическом институте разработана и применяется автоматизированная технология краткосрочного (с заблаговременностью до 72 часов) прогноза положения тропических циклонов северо-западной части Тихого океана с использованием численной региональной модели HWRF.

***Параметры, которые ограничивают использование:***
1) Ограниченная заблаговременность - решение ориентировано на краткосрочный прогноз с заблаговременностью до 72 часов.
2) Модель HWRF ориентирована на северо-западную часть Тихого океана.

_Материал:_  [https://vva.mil.ru/upload/site21/document_file/Pl6zK8lfF5.pdf](https://vva.mil.ru/upload/site21/document_file/Pl6zK8lfF5.pdf)

### 2. Joint Typhoon Warning Center (JTWC)
Совместный центр ВМС и ВВС США, базирующийся в Гонолулу, Гавайи. Он отслеживает и предоставляет прогнозы для тропических циклонов в Западной части Тихого океана и Индийском океане. JTWC использует спутниковые данные и другие источники для мониторинга циклонов, выпускает предупреждения и сотрудничает с метеорологическими центрами по всему миру. Работает в сфере безопасности, обеспечивая информацией военные и гражданские интересы.

***Параметры, которые ограничивают использование:***
1) JTWC фокусируется на Западной части Тихого океана и Индийском океане.
2) JTWC в первую очередь ориентирован на обеспечение безопасности военных и гражданских интересов.

_Материал:_ [https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C01107](https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C01107)

### 3. Detection of Tropical Cyclone using Deep Learning Network
Статья посвящена проекту по обнаружению тропических циклонов с использованием сетей глубокого обучения. Авторы рассматривают реализацию механизма прогнозирования циклонов по снимкам со спутника. Они создали систему идентификации объектов глубокого обучения для обнаружения циклонов, с основным вниманием на поиске вращающегося центра циклона.

***Параметры, которые ограничивают использование:***
1) Ограниченность набора данных
2) Неудовлетворительное объяснение модели
3) Сложность внедрения

_Материал:_  [https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4381923](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4381923)
  

# 📋Функциональные и нефункциональные требования
Было определено ожидаемое поведение и характеристики проекта. Функциональные требования описывают ключевые функции. Нефункциональные требования, в свою очередь, фокусируются на аспектах качества работы системы в различных условиях и различных пользовательских потребностей.

### Функциональные требования:

**1. Сбор данных**
Программа должна автоматически собирать спутниковые снимки с различных источников

**2. Детекция циклонов**
Система должна автоматически детектировать тропические циклоны на спутниковых снимках

**3. Выдача предупреждений**
Автоматическая генерация предупреждения и уведомления о приближающихся тропических циклонах

**4. Интерфейс**
Удобный интерфейс для визуализации данных, отображения тропических циклонов и получения актуальной информации

### Нефункциональные требования:

**1. Производительность**
Высокая энергоэффективность и производительность обработки и анализа данных для минимизации времени ответа

**2. Совместимость**
Программа должна быть совместимой с различными типами спутников и форматами данных

**3. Доступность**
Система должна быть доступной для пользователей с различными уровнями квалификации, включая метеорологов, исследователей и общественность

**4. Масштабируемость**
Эффективная обработка данных различных размеров

# ❕Общие и локальные ограничения
В данном пункте рассмотрены общие и локальные ограничения, которые следует учитывать при разработке и внедрении системы предупреждения циклонов.

### Общие ограничения:

**1. Законы о конфиденциальности данных**
Соблюдение законов о конфиденциальности данных при обработке и хранении информации

**2. Соблюдение авторских прав**
При использовании данных спутниковых снимков и других информационных ресурсов необходимо соблюдать авторские права и лицензионные соглашения

**3. Экологические стандарты**
Проект должен соответствовать экологическим стандартам, особенно в части использования энергии

**4. Международные нормы**
Если система предназначена для использования в различных странах, необходимо учитывать различия в законодательстве и следовать международным нормам

### Локальные ограничения:

**1. Требования к хранению данных**
Соблюдать локальные законы и требования относительно хранения данных.

**2. Законы о безопасности**
Соблюдать местные законы и стандарты в области безопасности, особенно, если система предоставляет информацию о приближающихся опасностях.

**3. Локальные культурные особенности**
Учитывать культурные нормы и ожидания, чтобы проект был соответствующим и принятым в соответствующей общественной среде.

**4. Недостаток спутниковых данных**
Без регулярного доступа к спутниковым снимкам система не сможет мониторить актуальные события.


# 🌐Технологическая основа
*Python* был выбран в качестве основного языка программирования, поскольку он является предпочтительным выбором для реализации нейронных сетей благодаря своей мощной поддержке библиотек машинного обучения, таких как *TensorFlow* и *PyTorch*. Кроме того, *Python* известен своим простым и читаемым синтаксисом, что облегчает разработку и поддержку кода, а также его широкое распространение в научном сообществе способствует доступности ресурсов и поддержке.

Также в проекте используются другие языки программирования и разметки для разработки интерфейса программы и создания рабочего прототипа, в их числе:
1. *JavaScript*
2. *HTML 5*
3. *CSS 3*

Для задачи обучения модели использовалась *YOLOv8*.

Для сбора и анализа статистических данных была использована библиотека *Eco2AI* от *SberAI*, что позволило эффективно анализировать информацию о процессе обучения и результате работы модели.

# 📚Подготовка датасета
Проанализировав набор данных от команды SberAI, было отмечено, что в нём присутствуют циклоны всех 6 классов опасности. Также было выявлено, что предоставленный набор данных находился не в том формате, который был необходим для обучения модели семейства YOLOv8. Был написан скрипт, чтобы привести все данные к нужному формату.

Изображение с требованиями по формату файла аннотации для модели YOLO c официального сайта:
![Picture](https://github.com/pocketgodru/Detection_cyclone/assets/104260621/85db9e09-b14a-4246-a7b0-6602a97449c4)

Изначальный формат данных в датасете:
![Picture](https://github.com/pocketgodru/Detection_cyclone/assets/104260621/60f27661-d6b6-4c3f-86ac-4f3a3f53f9d5)

Формат после обработки скриптом:
![Picture1](https://github.com/pocketgodru/Detection_cyclone/assets/104260621/9ec73d34-6849-4178-9760-517fb9f76746)

# 🤖Обучение модели
Прежде чем обучать модель было необходимо определиться с архитектурой нейронной сети.

Была выбрана модель YOLOv8, так как это последние семейство моделей обнаружения объектов на базе YOLO от Ultralytics, обеспечивающих самые современные характеристики.

После начался этап обучения модели на подготовленном датасете, включавший в себя 9530 фотографий. После обучение модели на 15 эпохах был проведен анализ обученной модели.
В процессе обучения модель демонстрировала постоянное снижение потерь как по ограничивающим рамкам (*box  loss*), так и по классификации (*class  loss*) и обнаружению объектов (*object  loss*), что свидетельствует о повышении точности и уверенности в предсказаниях модели. Ключевые показатели точности и полноты (*precision и recall*), а также средняя точность (*mAP*) на различных порогах пересечения показали положительную динамику улучшения производительности модели с течением времени. Эти результаты подтверждают эффективность выбранной архитектуры *YOLOv8* и предполагают ее пригодность для решения задачи распознавания тропических циклонов на спутниковых  снимках.

# 🔃Схема взаимодействия с моделью

1. Загрузка изображения.

2. Преобразование входных изображений к размеру 640x640 пикселей.

3. Обработка изображений моделью, включая разбиение на сетку и индивидуальный анализ каждой ячейки.

4. Конвертация вывода модели из процентного соотношения в пиксели для получения конечного результата.

5. Вывод результатов пользователю.

# 🎨Интерфейс пользователя
Дизайн и расположение элементов направлены на удобство и интуитивность использования. Пользовательская навигация ориентирована на последовательные шаги: от загрузки изображения до получения результатов. Все компоненты функциональны и ориентированы на выполнение одной 
задачи - обнаружение и анализ циклонов на изображениях.

***Компоненты интерфейса:***

**1. Заголовок страницы  "Обнаружение циклонов"**
Это верхний элемент, который даёт пользователю понять основную функцию страницы.

**2. Описание процесса  "Загрузите изображение вашего циклона"**
Этот раздел даёт инструкции пользователю о том, как использовать функцию: пользователь должен загрузить изображение циклона, который хочет обнаружить. Система затем проанализирует изображение и предоставит результаты.

**3. Кнопка "Выбрать файл"**
Эта кнопка позволяет пользователю выбрать файл из локальной файловой системы для загрузки.

**4. Текстовый маркер "Файл не выбран"**
Этот индикатор информирует пользователя о том, что файл еще не был выбран для загрузки.

**5. Кнопка "Загрузить изображение"**
После выбора файла пользователь может нажать эту кнопку для начала процесса загрузки и анализа изображения.

**6. Секция "Результаты"**
Здесь пользователь будет информирован о том, что после загрузки изображения результаты будут отображены в этом разделе. Это включает в себя информацию о том, был ли циклон обнаружен на изображении.

**7. Текст "Результаты появятся здесь после загрузки изображения."**
Это место, где будут отображаться результаты после анализа моделью загруженного изображения.

**8. Футер с контактной информацией**
В нижней части страницы находится футер, содержащий контактную информацию команды - "2024 {Svet} / АНО ДО Детский телефон "Кванториум" г. Ульяновск".

# 🔜Совершенствование проекта
**1.  Улучшение точности модели**
Дообучение модели на разнообразных снимках спутников для повышения точности распознавания циклонов.

**2.  Улучшение пользовательского интерфейса**
Усовершенствование интерфейса для повышения удобства использования.

**3. Модель предсказания**
Обучение модели для предсказания траектории, скорости ветра и классификация циклона для более полного анализа циклона.

# 📩Обратная связь

Если у Вас есть вопросы, обращайтесь на почту [project@dtcyclone.ru](mailto:project@dtcyclone.ru)

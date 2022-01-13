# dtp-stat
Разработка рекомендательной системы по выявлению опасных дорожных участков и предотвращению будущих дорожно-транспортных происшествий на территории регионов Российской Федерации

Данная система диагностики будет включать исследование имеющихся открытых данных по дорожно-транспортным происшествиям портала https://dtp-stat.ru, приложение-бот для анализа опасности дорожной ситуации по введенным данным окружения и интерфейс для взаимодействия с промоботом — сервисным роботом, оказывающим помощь в сборе данных и информировании посетителей чемпионата (https://promo-bot.ru).

Данные по ДТП доступны для загрузки на странице https://dtp-stat.ru/opendata/ и представлены в формате .geojson по всем регионам. Каждый файл имеет следующую структуру:
```
{
    "id": 384094, # идентификатор
    "tags": ["Дорожно-транспортные происшествия"], # показатели с официального сайта ГИБДД
    "light": "Светлое время суток", # время суток
    "point": {"lat": 50.6039, "long": 36.5578}, # координаты
    "nearby": [ "Нерегулируемый перекрёсток неравнозначных улиц (дорог)", "Жилые дома индивидуальной застройки"], # координаты
    "region": "Белгород", # город/район
    "address": "г Белгород, ул Сумская, 30", # адрес
    "weather": ["Ясно"], # погода
    "category": "Столкновение", # тип ДТП
    "datetime": "2017-08-05 13:06:00", # дата и время
    "severity": "Легкий", # тяжесть ДТП/вред здоровью
    "vehicles": [ # участники – транспортные средства
      {
        "year": 2010, # год производства транспортного средства
        "brand": "ВАЗ", # марка транспортного средства
        "color": "Иные цвета", # цвет транспортного средства
        "model": "Priora", # модель транспортного средства
        "category": "С-класс (малый средний, компактный) до 4,3 м", # категория транспортного средства
        "participants": [ # участники внутри транспортных средств
        {
          "role": "Водитель", # роль участника
          "gender": "Женский", # пол участника
          "violations": [], # нарушения правил участником
          "health_status": "Раненый, находящийся...", # состояние здоровья участника
          "years_of_driving_experience": 11 # стаж вождения участника (только у водителей)
        }
      ]
    },
  ],
  "dead_count": 0, # кол-во погибших в ДТП
  "participants": [], # участники без транспортных средств (описание, как у участников внутри транспортных средств)
  "injured_count": 2, # кол-во раненых в ДТП
  "parent_region": "Белгородская область", # регион
  "road_conditions": ["Сухое"], # состояние дорожного покрытия
  "participants_count": 3, # кол-во участников ДТП
  "participant_categories": ["Все участники", "Дети"] # категории участников
}
```
В настоящее время накоплено достаточно много данных по дорожно-транспортным происшествиям, включающих все подробности окружения, которые можно проецировать на другие, аналогичные, условия. В результате анализа таких данных можно выявить дорожные участки и перекрёстки, требующие наибольшего внимания в плане перепроектирования или реорганизации движения на них. Предложенные решения помогут в будущем снизить или вообще предотвратить количество дорожно-транспортных происшествий. Актуальность повышения безопасности дорожного движения заложена в международной программе Vision Zero https://ru.wikipedia.org/wiki/Vision_Zero, которая активно обсуждается с 2010-х годов в России.

В рамках всего конкурсного задания потребуется предобработать данные, выполнить анализ данных и выявить ключевые зависимости, построить необходимые модели машинного обучения, разработать приложение-бот и интерфейс взаимодействия с роботом-промоботом для сбора данных и информирования посетителей чемпионата.

На этой сессии необходимо подготовить набор данных и произвести его предобработку для дальнейшего исследования и построения моделей обучения, а также запрограммировать промобот для сбора данных у посетителей чемпионата.

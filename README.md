# Продуктовая аналитика интернет-магазина

Сквозной учебный проект: от загрузки данных до дашборда. Считаю продуктовые
метрики на реальных данных и собираю BI-дашборд.

## Данные
- RetailRocket (события пользователей): kaggle.com/datasets/retailrocket/ecommerce-dataset
- Cookie Cats (A/B-тест): kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats
Сырые данные в репозиторий не коммитятся (папка data/), скачиваются по ссылкам выше.

## Что сделано
- REST API: получение справочных данных через requests + парсинг JSON (01_api)
- Воронка view -> корзина -> покупка и конверсия по шагам (02_funnel)
- Retention по когортам с поправкой на окно наблюдения (03_retention)
- A/B-тест размещения гейта: z-тест долей по retention_1 и retention_7 (04_ab_test)
- Экспорт агрегатов и подготовка данных (melt) для BI (05_export)
- Дашборд в Yandex DataLens: воронка, retention-кривая, A/B-сравнение

## Ключевые выводы
- Узкое место воронки — переход просмотр -> корзина (конверсия ~2.7%)
- Retention-кривая резко падает в первые дни, затем выходит на плато
- Перенос гейта с 30 на 40 уровень значимо снижает retention_7 (p ~ 0.002),
  на retention_1 значимого эффекта нет

## Стек
Python (pandas, matplotlib, statsmodels), REST API, Google Sheets, Yandex DataLens, Git
EOF
# Курсовой проект по фреймворкам Python для анализа данных

Сравниваем, как ручное и искусственное обогащение данных влияет на качество и устойчивость моделей.

## Данные

- [Отзывы о товарах](https://huggingface.co/datasets/ai-forever/ru-reviews-classification/tree/0f67d914f396ce22917dc6463ec619799b3b08d2). Скачайте `train.jsonl`, `validation.jsonl` и `test.jsonl` в `data/raw/reviews/`.
- [Фото со стройки, Roboflow v8](https://universe.roboflow.com/constructionsatefy/bac_hien_construction_safety_2024/dataset/8). Скачайте выгрузку в формате COCO JSON и распакуйте в `data/raw/safety/`. В папках `train/`, `valid/` и `test/` должны лежать фото и файлы `_annotations.coco.json`.

Папка `data/` хранится только локально и не входит в репозиторий.

## Запуск

Нужен Python 3.12 или новее. Из корня проекта:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -e .
python -m jupyter lab
```

Откройте нужный ноутбук и выполните ячейки по порядку.

- [reviews.ipynb](notebooks/reviews.ipynb) готовит 3 000 отзывов для классификации тональности, по 1 000 на класс. В train 1 800 записей, в validation и test по 600. Выборки сохраняются в `data/processed/reviews/`.
- [helmets.ipynb](notebooks/helmets.ipynb) отбирает 4 000 фотографий с 10 631 рамкой классов `Helmet`, `No-Helmet` и `Person`. В train 3 200 фото, в valid и test по 400. Список фото и рамки формируются в ноутбуке.

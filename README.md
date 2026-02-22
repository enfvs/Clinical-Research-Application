# Clinical-Research-Application

Репозиторий с двумя учебными исследованиями медицинских данных в формате Jupyter Notebook.

Внутри:
- **Набор 1: клиническое исследование** - проверка гипотезы о различиях между группами (препарат против плацебо)
- **Набор 2: диабет** - построение модели классификации (логистическая регрессия) и интерпретация признаков

## Что есть в проекте

- `task1_clinical_trial_analysis.ipynb`
  - загрузка данных и базовые проверки
  - визуальный анализ (гистограммы, boxplot)
  - проверка предпосылок
    - Shapiro-Wilk (нормальность)
    - Levene (равенство дисперсий)
  - выбор критерия и проверка гипотезы
    - t-test или Mann-Whitney U
  - размер эффекта (Cohen's d)

- `task2_diabetes_analysis.ipynb`
  - исследование данных, пропуски и аномалии
  - корреляционный и визуальный анализ
  - подготовка признаков
  - модель LogisticRegression + метрики
    - accuracy, precision, recall, f1
    - ROC curve и ROC-AUC
    - confusion matrix
  - коэффициенты модели и функция `predict_diabetes`
  - бонус: подбор гиперпараметров через GridSearchCV

## Структура репозитория

```
.
├─ task1_clinical_trial_analysis.ipynb
├─ task2_diabetes_analysis.ipynb
├─ README.md
└─ LICENSE
```

## Данные

Датасеты в репозиторий не включены.

Ожидаемые файлы:
- для задания 1: `clinical_trial_data.csv` (или `clinical_trial_data222.csv`)
- для задания 2: `diabetes.csv` (или `diabetes222.csv`)

Куда положить:
- в корень проекта, или
- в папку `src/` (если ты ее создашь).

Оба ноутбука ищут файлы по нескольким путям, например: `./diabetes.csv` и `./src/diabetes.csv`.

### Ожидаемые поля (минимум)

**Набор 1 (клиническое исследование):**
- колонка с группой: по умолчанию `Group`
- колонка с показателем: по умолчанию `Score`

Если названия отличаются, в ноутбуке можно поменять переменные `group_col` и `score_col`.

**Набор 2 (диабет):**
- целевая колонка: `Outcome` (0/1)

## Быстрый старт

### 1) Создать окружение и поставить зависимости

```bash
python -m venv .venv

# Linux/macOS
source .venv/bin/activate

# Windows
# .venv\Scripts\activate

pip install -U pip
pip install numpy pandas matplotlib seaborn scipy scikit-learn jupyter
```

### 2) Запустить Jupyter

```bash
jupyter lab
# или
jupyter notebook
```

Открой нужный ноутбук:
- `task1_clinical_trial_analysis.ipynb`
- `task2_diabetes_analysis.ipynb`

## Примечания

- Если ноутбук падает с ошибкой `FileNotFoundError`, проверь названия файлов и расположение (корень проекта или `src/`).
- Рекомендуется перезапустить ядро и запустить все ячейки (в Jupyter обычно это пункт меню `Restart kernel and run all`), чтобы получить воспроизводимый результат.

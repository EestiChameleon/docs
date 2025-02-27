# Точечная диаграмма ![](../../_assets/datalens/scatter-chart.svg)

Точечная диаграмма показывает отношение между двумя величинами (измерениями или показателями). Их значения показываются в виде точек. На точечной диаграмме всегда есть две оси: набор значений одной величины представлен вдоль горизонтальной оси, а другой — вдоль вертикальной. На пересечении координат X и Y отображается точка данных, которая связывает эти два значения. Такие точки данных могут быть распределены по горизонтальной оси равномерно или неравномерно, в зависимости от конкретных данных.

Диаграмму используют, когда нужно найти зависимость между измерениями и показателями или показать разброс значений. Например, соотношение между средним чеком на товар и числом заявок.

Также зависимости на точечной диаграмме можно показывать с помощью размера точек. Размер точки определяется значением показателя: чем больше значение показателя, тем больше размер точки. Например, размер точки может зависеть от скидки на товар. 

![scatter-chart](../../_assets/datalens/visualization-ref/scatter-chart/scatter-chart.png)

{% cut "Срез из пяти строк исходной таблицы" %}

Продукт | Категория | Средний чек | Число заявок | Скидка	
----|----|----|----|-----|
Раствор для мытья полов|	Бытовая химия|	153.0 | 1 | 0 |
Мультиварка с 40 режимами готовки еды|	Техника для дома |	3442.0 | 1 | 0 |
Гель для стирки цветных вещей|	Бытовая химия |	525.0 | 1 | 0 |
Порошок для чистки ковриков|	Бытовая химия | 463.0 | 1 | 0 |
Средство для мытья посуды с ароматом лимона|	Бытовая химия| 362.0 | 1 | 0 |

Датасет построен на основе таблиц подключения [Sample ClickHouse](../quickstart.md).

{% endcut %}

Вы можете использовать градиент на диаграмме, добавив показатель в секцию **Цвета**. Например, чем выше средний чек продукта, тем темнее оттенок точки.

![scatter-chart](../../_assets/datalens/visualization-ref/scatter-chart/gradient-scatter-chart.png)

## Секции в визарде {#wizard-sections}

Секция<br/> в визарде| Описание
----- | ----
X | Измерение или показатель. Задает значение по оси X.
Y | Измерение или показатель. Задает значение по оси Y.
Точки | Измерение. Определяет количество точек на диаграмме.
Размер точек | Показатель. Задает размер точки в зависимости от значения показателя.
Цвета | Измерение или показатель. Влияет на цвет точек.
Сортировка | Измерение. Может использоваться только измерение с оси Х. Влияет на сортировку оси X.
Фильтры | Измерение или показатель. Используется в качестве фильтра.

## Создание точечной диаграммы {#create-diagram}

Чтобы создать точечную диаграмму:

1. На [главной странице]({{link-datalens-main}}) сервиса {{ datalens-full-name }} нажмите **Создать чарт**.
1. В разделе **Датасет** выберите датасет для визуализации. Если у вас нет датасета, [создайте его](../operations/dataset/create.md).
1. Выберите тип чарта **Точечная диаграмма**.
1. Перетащите измерение из датасета в секцию **X**.
1. Перетащите один или несколько показателей из датасета в секцию **Y**. Значения отобразятся в виде точек на пересечении осей X и Y.

Дополнительно вы можете: 

1. Изменить цвет точек:

   1. Перетащите измерение или показатель в секцию **Цвета**.
   1. Нажмите значок ![](../../_assets/datalens/gear.svg) и установите новые цвета.

1. Указать дополнительное измерение. Для этого перетащите измерение в секцию **Точки**.

### Настройка отображения пустых (`null`) значений {#null-settings}

{% include [datalens-chart-null-settings](../../_includes/datalens/datalens-chart-null-settings.md) %}

## Рекомендации {#recomendations}

* {% include [datalens-category-text](../../_includes/datalens/datalens-category-text.md) %}
* Масштаб на осях зачастую разный, при этом может не начинаться от 0. Обращайте внимание на подписи значений.
* Точечная диаграмма не подходит для визуализации данных во времени.
* При визуализации нескольких показателей внимательно подбирайте цвета. Они должны быть различимыми и контрастными.


---
"date": "2025-04-24"
"description": "Узнайте, как создавать и управлять правилами резервного копирования шрифтов с помощью Aspose.Slides для Python, чтобы гарантировать единообразие ваших презентаций в разных системах."
"title": "Освоение возврата шрифтов в Aspose.Slides для Python&#58; Полное руководство"
"url": "/ru/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение возврата шрифтов в Aspose.Slides для Python: подробное руководство

## Введение

Проблемы совместимости шрифтов могут стать проблемой при создании презентаций, особенно если символы Unicode не поддерживаются основными шрифтами. **Aspose.Slides для Python** обеспечивает надежное решение с помощью правил резервного копирования шрифтов, гарантируя визуальную привлекательность и читаемость вашей презентации в различных системах.

В этом руководстве мы рассмотрим, как создавать и управлять правилами резервного копирования шрифтов с помощью Aspose.Slides для Python. Вы узнаете:
- Настройка вашей среды с помощью Aspose.Slides
- Создание коллекции правил резервного копирования шрифтов
- Управление этими правилами путем добавления или удаления шрифтов на основе диапазонов Unicode.
- Применение правил к презентациям и отображение слайдов в виде изображений

Давайте начнем с подготовки вашей среды.

## Предпосылки

Убедитесь, что ваша среда готова к этой задаче. Вот что вам понадобится:
1. **Aspose.Slides для Python**: Эта библиотека управляет правилами резервного копирования шрифтов.
2. **Среда Python**: Убедитесь, что установлен Python (версии 3.6 или более поздней).
3. **Базовые знания Python**: Знакомство с синтаксисом и концепциями Python будет полезно при изучении фрагментов кода.

## Настройка Aspose.Slides для Python

### Установка

Для начала установите библиотеку Aspose.Slides с помощью pip:

```bash
pip install aspose.slides
```

### Приобретение лицензии

Aspose предлагает бесплатную пробную лицензию для изучения его функций без ограничений. Вот как вы можете ее получить:
- Посещать [Страница покупки Aspose](https://purchase.aspose.com/buy) для приобретения опций или доступа к временной лицензии.
- В качестве альтернативы загрузите бесплатную пробную версию с сайта [Раздел загрузок](https://releases.aspose.com/slides/python-net/).

### Базовая инициализация

После установки инициализируйте Aspose.Slides в вашем скрипте Python:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Руководство по внедрению

### Создание и управление правилами резервного копирования шрифтов

#### Обзор

Правила резервного шрифта гарантируют, что все символы в презентации будут иметь соответствующий шрифт, сохраняя читаемость для языков с уникальными наборами символов.

#### Этапы внедрения

**1. Создайте коллекцию правил резервного копирования шрифтов**

Начните с создания коллекции для определения резервных шрифтов:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Добавьте правило резервного шрифта**

Определите правило, указывающее диапазон Unicode и резервный шрифт:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Параметры**: `0x400` это начало диапазона Unicode, `0x4FF` это конец, и `"Times New Roman"` является резервным шрифтом.

**3. Управление существующими правилами**

Повторите каждое правило, чтобы изменить его по мере необходимости:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Удалить правило**

При необходимости удалите первое правило из вашей коллекции:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Применение правил резервного копирования шрифтов к презентации и визуализация изображения

#### Обзор

После настройки правил резервного шрифта примените их к презентациям, чтобы гарантировать, что текст при необходимости использует указанные резервные шрифты.

#### Этапы внедрения

**1. Инициализируйте свою среду**

Подготовьте каталоги для ввода и вывода:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Применение резервных правил к презентации**

Загрузите файл презентации и примените правила шрифта:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
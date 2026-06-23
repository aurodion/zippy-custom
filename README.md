# zippy-custom
# 🧮 Універсальний конвертер цін — розширення для Zippy CRM

> Вбудований інструмент для швидкого розрахунку роздрібної ціни товару при додаванні нової позиції у прибуткову накладну.

![Zippy CRM](https://img.shields.io/badge/Zippy-CRM-blue?style=flat-square)
![Bootstrap](https://img.shields.io/badge/Bootstrap-4-7952B3?style=flat-square&logo=bootstrap)
![Vanilla JS](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat-square&logo=javascript)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

---

## 📋 Опис

Розширення додає компактний калькулятор прямо у форму додавання товару (`goodsreceipt.html`). Дозволяє менеджеру миттєво розрахувати відпускну ціну з урахуванням курсу валюти та коефіцієнта націнки — без виходу з форми.

**Підтримує два режими:**

| Режим | Опис |
|-------|------|
| 💱 **Валюта** | Ціна у валюті × курс → UAH чиста → UAH з націнкою |
| 🇺🇦 **Гривня** | Вхідна ціна в грн → одразу множиться на коефіцієнт |

---

## ✨ Функції

- **Миттєвий розрахунок** — результат оновлюється при кожному натисканні клавіші
- **Два режими** — з валюти або суто гривня (перемикання радіокнопками)
- **Копіювати одним кліком** — кнопка «Копіювати» поруч з кожним результатом
- **Пам'ять сесії** — курс, коефіцієнт та режим зберігаються між переходами (`sessionStorage`)
- **Адаптивні поля** — при режимі «гривня» зайві поля автоматично ховаються
- **Підтримка коми** — можна вводити `45,5` або `45.5`

---

## 📸 Скріншот

<p align="center">
  <img src="goodsreceipt-converter/screenshot.jpg" alt="Скріншот конвертера" width="360">
</p>

---

## 🚀 Встановлення

### 1. Відкрийте файл шаблону

```
templates/pages/doc/goodsreceipt.html
```

### 2. Знайдіть блок кнопок форми

```html
<div class="form-group">
    <input type="button" zippy="cancelrow" value="До переліку" class="btn btn-secondary mr-2">
    <input zippy="saverow" type="submit" value="Зберегти" class="btn btn-primary">
</div>
```

### 3. Вставте код конвертера одразу після цього блоку

Вставте вміст файлу [`converter.html`](goodsreceipt-converter/converter.html) після закриваючого тегу `</div>`.

---

## 📁 Файли репозиторію

```
📦 zippy-price-converter
 ├── 📄 README.md          # Ця документація
 ├── 📄 goodsreceipt-converter/converter.html     # Код конвертера (вставляється в шаблон)
 └── 🖼️ goodsreceipt-converter/screenshot.jpg    # Скріншот інтерфейсу
```

---

## ⚙️ Налаштування за замовчуванням

У файлі `converter.html` можна змінити початкові значення:

```html
<!-- Курс валюти за замовчуванням -->
<input ... id="conv_rate" value="45" ...>

<!-- Коефіцієнт націнки за замовчуванням -->
<input ... id="conv_margin" value="1.3" ...>
```

> Після першого використання значення зберігаються у `sessionStorage` браузера автоматично.

---

## 🧩 Сумісність

- ✅ Zippy (ZStore) PHP Framework
- ✅ Bootstrap 4
- ✅ Сучасні браузери (Chrome, Firefox, Edge)
- ✅ Темна тема CRM «з коробки»

---

## 📄 Ліцензія

MIT — використовуйте вільно, модифікуйте як завгодно.

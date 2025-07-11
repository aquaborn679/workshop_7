# 🧪 Лабораторная работа №7

---

## 1.3 — Управление движением

> Движение реализовано через метод `AddRelativeForce()` по вводу **`Horizontal`** и **`Vertical`**.  
> Скорость зависит от переменных `speed` и `maxSpeed`.

---

## 2.4 — Настройка выстрела

> Чтобы выстрел работал корректно:
>
> - Назначить **префаб пули** в поле `BulletPrefab` в инспекторе;
> - Убедиться, что у пули есть компонент **Rigidbody**;
> - Отключён параметр **Use Gravity**;
> - Установлен тег **"Bullet"**;
> - Объект **`BulletSpawner`** размещён в нужной точке (на конце оружия);
> - К объекту подключён скрипт `BulletSpawner.cs`.

---

## 3.3 — Разрушение врага

> Скрипт `Enemy` отслеживает столкновения.  
> При столкновении с объектом с тегом **"Bullet"** вызывается метод `ExplodeCube()`.  
>
> Он:
> - Создаёт 64 маленьких кубика (4×4×4) в форме решётки;
> - Применяет к каждому силу взрыва;
> - Уничтожает исходный объект `Enemy`.
>
> Это создаёт эффект **визуального разрушения врага** при попадании.

---

## 3.6 — Выбор силы взрыва

> Значение `explodeForce = 400f` оказалось оптимальным:  
> - **Меньше** — кусочки почти не двигаются;  
> - **Больше** — разлетаются слишком быстро и теряются;  
> - **400** — выглядит естественно и красиво в игре.

---

## 4.4 — Звук разрушения

> - Создан отдельный объект `EnemySound` с компонентом **AudioSource**;
> - В объект `Enemy` добавлена ссылка на этот звук;
> - В `Enemy.cs` добавлена переменная `public AudioSource audioSource;`;
> - В методе `ExplodeCube()` вызывается `audioSource.Play();`.
>
> Это позволяет **проигрывать звук**, не удаляя его вместе с врагом.

---

## 5.4 — Счёт и его сохранение

> Проблема: переменная очков внутри `Enemy` — **обнуляется при уничтожении**.  
> Решение:
> - Создать отдельный объект `Progress` со скриптом;
> - Сделать его **синглтоном**;
> - Хранить очки **вне врагов**;
>
> Тогда значение счёта будет сохраняться между врагами.

---

## 6.2 — Условие перезагрузки

> Логика перезагрузки сцены добавляется в метод `AddScore()` внутри `Enemy.cs`.  
> Это позволяет **проверять количество очков** каждый раз после попадания по врагу.

---

## ✅ 6.4 — Итог

> В этой лабораторной работе я:
> - Создал механику **стрельбы от первого лица**;
> - Реализовал **визуальный и звуковой отклик**;
> - Добавил **счётчик очков** и **условие перезагрузки**;
>
> Работа помогла лучше понять **взаимодействие объектов, скриптов и UI** в Unity.

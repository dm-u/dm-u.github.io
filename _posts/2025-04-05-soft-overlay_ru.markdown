---
layout: post
title:  "Soft Overlay: лучшая замена для Soft Light и Overlay"
date:   2025-04-05 00:00:00 +0300
categories: photoshop
---

# Лучший режим наложения для Dodge & Burn

Похоже, я нашёл лучший режим наложения для dodge&burn. И это не Soft Light и не Overlay.

Dodge&Burn — главный инструмент в арсенале каждого ретушера. Эта техника позволяет локально осветлять или затемнять отдельные области фотографии, создавая объем, акценты и исправляя дефекты. По сути, мы имитируем то, что фотограф мог бы сделать на съемке с дополнительным освещением — если бы у него было бесконечное количество источников света, времени и терпения.

Технически Dodge&Burn можно реализовать разными способами: инструменты Dodge Tool и Burn Tool, кривые, корректирующие слои. Но удобнее всего использовать контрастный корректирующий слой Soft Light (чаще) или Overlay (реже), потому что ретушь выполняется в одном слое.

Каким должен быть идеальный режим наложения для dodge&burn? Если кратко, он должен имитировать изменение освещенности отдельных участков сцены. Или экспозиции. Звучит просто. Но такого режима наложения в Photoshop нет.

Давайте просто посмотрим, как работают обычные инструменты dodge&burn и проверим, насколько они близки к изменению экспозиции.

## Overlay

![IMG_3549.jpg](/assets/IMG_3549.jpg)
![IMG_3549_plus_1EV_Overlay.jpg](/assets/IMG_3549_plus_1EV_Overlay.jpg)

Слева — конвертация с правильной экспозицией, справа — конвертация с экспозицией -1EV и осветление в Photoshop при помощи Overlay. Видны заметные сдвиги по цветовому тону и насыщенности.

![IMG_3549_minus_1EV.jpg](/assets/IMG_3549_minus_1EV.jpg)
![IMG_3549_minus_1EV_Overlay.jpg](/assets/IMG_3549_minus_1EV_Overlay.jpg)

Слева — конвертация с экспозицией -1EV. Справа — конвертация с правильной экспозицией и затемнение в Photoshop при помощи Overlay. Больше так делать не будем.

## Soft Light

Soft Light действует аккуратнее и является выбором "по умолчанию".

![IMG_3549.jpg](/assets/IMG_3549.jpg)
![IMG_3549_plus_1EV_Soft_Light.jpg](/assets/IMG_3549_plus_1EV_Soft_Light.jpg)

Слева — конвертация с правильной экспозицией, справа — конвертация с экспозицией -1EV и осветление в Photoshop при помощи Soft Light. Видна сильная потеря насыщенности, контраста и деталей в светах.

![IMG_3549_minus_1EV.jpg](/assets/IMG_3549_minus_1EV.jpg)
![IMG_3549_minus_1EV_Soft_Light.jpg](/assets/IMG_3549_minus_1EV_Soft_Light.jpg)

Слева — конвертация с экспозицией -1EV. Справа — конвертация с правильной экспозицией и затемнение в Photoshop при помощи Soft Light. Видны сильное повышение контраста и насыщенности. Возможно, в каких-то случаях это будет плюсом, но наша цель — имитация экспозиции.

## Soft Overlay

Итак, ни Overlay, ни Soft Light не дают нам того, что нужно – естественных изменений освещенности. Здесь мы должны смириться с несовершенством инструментов и просто по ситуации выбирать наиболее подходящий. Либо использовать кривые или Brightness/Contrast для осветления и затемнения, постоянно переключаясь между слоями.

Но посмотрите на следующие примеры:

![IMG_3549.jpg](/assets/IMG_3549.jpg)
![IMG_3549_plus_1EV_Soft_Overlay.jpg](/assets/IMG_3549_plus_1EV_Soft_Overlay.jpg)

Слева — конвертация с правильной экспозицией, справа — конвертация с экспозицией -1EV и осветление в Photoshop при помощи Soft Overlay. Достойный результат.
Слева — конвертация с экспозицией -1EV. Справа — конвертация с правильной экспозицией и затемнение в Photoshop при помощи Soft Overlay. Это действительно два разных изображения, я проверил.

Кажется, это то, что нужно! Этот "режим наложения" называется Soft Overlay. Его нет среди стандартных режимов наложения, но все необходимые ингредиенты для его создания существуют уже 30 лет.

Soft Overlay создается следующим образом:
1. Создать корректирующий слой Invert.
2. Создать растровый слой с заливкой серым. Применить режим наложения Soft Light. На этом слое будет выполняться dodge&burn.
3. Создать корректирующий слой Invert и применить его в режиме Clipping Mask к предыдущему растровому слою.
4. Создать корректирующий слой Invert.

Adobe, спасибо за самый бесполезный корректирующий слой Invert! Кто бы мог подумать, что применив его три раза, мы получим нечто действительно полезное.

Должна получиться такая структура слоев:

![layers.png](/assets/layers.png)

Остается только перечислить преимущества Soft Overlay и объяснить, почему он работает именно так.

Итак, преимущества:
1. Один растровый слой. Без масок.
2. Сохранение точки черного.
3. Сохранение точки белого.
4. Лучшая имитация изменения экспозиции (пункт со звездочкой). Результат максимально приближен к тому, как если бы фотограф изменил освещение или экспозицию при съемке.
5. Минимальные сдвиги по цветовому тону и насыщенности. Кожа остается кожей.

Почему это работает? В технические аспекты погружаться не будем и ограничимся следующей картинкой:

![curves.png](/assets/curves.png)

Режим Soft Overlay — что-то среднее между Soft Light и Overlay. От Soft Light он взял мягкость. От Overlay — бережное отношение к теням. И от себя добавил адекватную коррекцию светов.

В более технических терминах, Soft Overlay — это сочетание Color Dodge и Multiply с зафиксированной точкой белого.

Недостаток один. Может не хватить силы воздействия. Но в этом случае можно создать еще один растровый слой с инвертирующим его слоем.


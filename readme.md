Author: @minixwz | Автор: @minixwz
GitHub: @minixwzm

Instructions in Russian and English language


© All rights reserved ©

Полный процесс от начала до конца


Установите зависимости:

pip install ultralytics opencv-python pyautogui mss pillow pynput либо pip install -r requirements.txt


Запустите сбор данных:

cd scripts
python capture_data.py


Что делать:

· Запустите скрипт
· Быстро перейдите в игру/программу где нужно наводить мышку
· Скрипт автоматически сделает 50 скриншотов с интервалом 3 секунды
· Меняйте ситуацию в игре - разные враги, разные позиции


Установите LabelIMG:

pip install labelImg
# или скачайте с GitHub: https://github.com/HumanSignal/labelImg

Запустите разметку:

labelImg

Настройте LabelIMG:

1. Open Dir → выберите data/images/train/
2. Change Save Dir → выберите data/labels/train/
3. Format → выберите YOLO
4. Создайте классы:
   · Нажмите Edit → Create RectBox
   · Введите имя класса (например: "enemy", "resource", "button". У нас уже стоит: "t" - Террорист, "ct" - Спецназ, "th" - Голова Террориста, "cth" - Голова Спецназа, "tt" - Торс террориста, "ctt" - Торс спецназ.)

   · Нарисуйте прямоугольник ВОКРУГ цели куда нужно кликать
   · Сохраните (Ctrl + S)

Процесс разметки:

1. Откройте первый скриншот
2. Нарисуйте прямоугольник вокруг цели
3. Укажите класс
4. Сохраните
5. Перейдите к следующему (Ctrl + D)
6. Повторите для всех 50-100 скриншотов

Важно: Укажите ПОЛНЫЙ путь к папке data!

Запустите обучение:

cd scripts
python train_gpu.py


После обучения, запускаем тест нашей модельки:

python test_model.py


Убедитесь, что модель правильно находит цели!

После всех тестов и обучений запустите саму модельку:

python aim_bot_advanced.py


Управление:

· F1 - включить/выключить скрипт
· F2 - полностью выйти
· ESC - экстренный выход

Краткая памятка по шагам:

1. python capture_data.py - собрать скриншоты
2. Запустить LabelIMG - разметить цели на скриншотах
3. Настроить data.yaml - указать пути и классы
4. python train_gpu.py - обучить модель
5. python test_model.py - проверить работу
6. python aim_bot_advanced.py - запустить готовый скрипт

Советы:

· Начните с малого: 50-100 скриншотов для начала (для более лучшего результата желательно 1000-2000)
· Разнообразные данные: разные ракурсы, освещение, размеры целей
· Качество разметки: точно обводите цели

© Авторские права защищены ©



Full process from start to finish

Install dependencies:
pip install ultralytics opencv-python pyautogui mss pillow pynput or pip install -r requirements.txt

Start data collection:
cd scripts
python capture_data.py

What to do:

· Run the script
· Quickly switch to the game/application where you need to aim the mouse
· The script will automatically take 50 screenshots with a 3-second interval
· Change the situation in the game - different enemies, different positions

Install LabelIMG:

pip install labelImg or download from GitHub:https://github.com/HumanSignal/labelImg

Start labeling:

labelImg

Configure LabelIMG:

1. Open Dir → select data/images/train/
2. Change Save Dir → select data/labels/train/
3. Format → select YOLO
4. Create classes:
   · Click Edit → Create RectBox
   · Enter class name (for example: "enemy", "resource", "button". We already have: "t" - Terrorist, "ct" - Counter-Terrorist, "th" - Terrorist Head, "cth" - Counter-Terrorist Head, "tt" - Terrorist Torso, "ctt" - Counter-Terrorist Torso)
   · Draw a rectangle AROUND the target where you need to click
   · Save (Ctrl + S)

Labeling process:

1. Open the first screenshot
2. Draw a rectangle around the target
3. Specify the class
4. Save
5. Go to the next one (Ctrl + D)
6. Repeat for all 50-100 screenshots

Important: Specify the FULL path to the data folder!

Start training:

cd scripts
python train_gpu.py

After training, test our model:
python test_model.py

Make sure the model correctly detects targets!

After all tests and training, run the main model:
python aim_bot_advanced.py

Controls:

· F1 - enable/disable script
· F2 - exit completely
· ESC - emergency exit

Quick step-by-step guide:

1. python capture_data.py - collect screenshots
2. Run LabelIMG - label targets on screenshots
3. Configure data.yaml - specify paths and classes
4. python train_gpu.py - train model
5. python test_model.py - test performance
6. python aim_bot_advanced.py - run final script

Tips:

· Start small: 50-100 screenshots for beginning (for better results, 1000-2000 is recommended)
· Diverse data: different angles, lighting, target sizes
· Labeling quality: accurately outline targets
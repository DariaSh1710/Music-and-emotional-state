Тема: Аналіз впливу музичної терапії на емоційний стан людини

1. Опис  та мета проєкту: 
Музика відіграє важливу роль у нашому житті, впливаючи на наші емоції, настрій і психічне становище. Однак, як прослуховування музики корелює з психічним здоров'ям людини залишається питанням для дослідження. Це дослідження має на меті виявити можливі кореляції між часом прослуховування, музичними вподобаннями  і психічним здоров'ям людини.
Для досягнення цієї мети, планую провести аналіз музичних пристрастей різних осіб, загальний рівень їх психоемоційного стану та часу прослуховування. Аналіз отриманих даних дозволить нам встановити, чи існує статистично значима кореляція між прослуховуванням музики та психічним здоров'ям. Результати цього дослідження можуть мати важливе значення для розуміння впливу музики на психічне здоров'я та для розвитку ефективних методів психотерапії чи підтримки психічного здоров'я через музичні впливи.

2. Вибір Технологій:
Для аналізу використовувались інструменти, які вивчалися протягом курсу: Python та бібліотеки pandas  та matplotlib для обробки даних, візуалізацій та статистичних розрахунків, Tableau для створення дашборду та візуалізації, Excel - для проведення статистичних розрахунків, сегментації та первинної обробки даних.

Етапи проекту: 

3. Збір та очищення даних:
Проведено збір даних з платформи Kaggle. За допомогою Excel була проведена первинна обробка даних, очищення пропусків, перетворення текстових значень у дату.

4. Аналіз даних:

         4.1. За допомогою Excel був проведений регресійний аналіз та розраховані наступні коефіцієнти. Була проаналізована залежність між кількістю часу витраченого на прослуховування музики та значенням, що відповідає за психоемоційний стан людини.
Статистика регресії:
●	R Square (Коефіцієнт детермінації): 0,0221. Це вказує, що тільки 2,21% змін у залежній змінній пояснюються незалежною змінною. Це дуже низький показник, що вказує на слабкий вплив незалежної змінної на залежну.
●	F-статистика: 16,57. Це показник того, наскільки модель пояснює зміну в залежній змінній. Високе значення F-статистики вказує на те, що модель є статистично значущою.
Коефіцієнти:
●	P-value: 0,00005. Дуже низьке значення P-значення вказує на значущість коефіцієнта.
Висновок:
Модель є статистично значущою, але коефіцієнт детермінації (R²) залишається низьким, що вказує на слабкий вплив незалежної змінної (кількість годин прослуховування музики) на залежну змінну (показники стану депресії).

4.2. Проведемо кореляційний аналіз даних за допомогою Python (бібліотеки pandas)  та побудуємо візуалізацію за допомогою matplotlib:

Посилання на проект: 

https://drive.google.com/file/d/1q-iFB9MD60rGI9SoZBL0gUJLgur39cRF/view?usp=sharing

import pandas as pd
data = pd.read_csv('kor.csv')

correlation = data['Hours per day'].corr(data['Total level'])
correlation
0.15086905986215637

Отриманий коефіцієнт кореляції  між змінними "Години прослуховування в день" та "Загальний рівень психо-емоційного стану" дорівнює приблизно 0.1509. Це значення не дуже велике, що вказує на досить слабкий або можливо відсутній зв'язок між цими двома змінними у вашому наборі даних.

Побудуємо графік для кращої візуалізації:

import matplotlib.pyplot as plt

plt.scatter(data['Hours per day'], data['Total level'])
plt.xlabel('Hours per day')
plt.ylabel('Total level')
plt.title('Графік розсіювання між годинами прослуховування і загальним рівнем психологічного стану')
plt.show()

 
4.3. Сегментація даних:
За допомогою Excel проведемо сегментацію нашої вибірки по кількості годин, що прослуховується в розрізі особистісних ефектів в психоемоційному стані.
Провівши сегментацію, у групі людей, що мають позитивний ефект від прослуховування музики ( а це найбільша частка - 547  чоловік) - можна побачити тенденцію, що позитивний ефект від прослуховування спостерігається у тих хто слухає музику до 2 годин в день. У людей в групах ( Покращення та  Відсутність ефекту), які слухають музику більше 6 годин на день можна спостерігати підвищення та погіршення показників психоемоційного стану.

4.4. 	 Також за допомогою надбудови в Excel - Pivot Table - виведемо середнє значення оцінки психоемоційного стану людини в розрізі музичного ефекту. 
Як можна побачити, що у людей з високим ступенем розладу (бал - 22,17) - спостерігається погіршення від прослуховування музики, натомість люди з більшим низьким, задовільним станом (15,46 - бал) - не відчувають ніяких ефектів. Найбільша частка  людей ( 547 чоловік) - мають середній ступінь розладу, та відчувають значне покращення від музики. 

5. Візуалізація та Дашборд :

https://public.tableau.com/app/profile/dariya.shyian/viz/project_17148324378170/sheet6

Наступним кроком дослідження є візуалізація отриманих результатів у Tableau Public.
Провівши опитування і побудувавши візуалізацію, яка оцінює вплив музики на стан людини, можна побачити, що більшість людей із вибірки - 542 особи із 728 чоловік відчувають позитивний ефект.
Була проведена візуалізація музичних жанрів, які найкраще впливають на психоемоційний стан людини.  Найбільш популярними серед слухачів є напрямки - Rock, Pop, Metal та Classic. Ці жанри представляють різноманітний спектр музичних стилів, що дозволяє припустити, що людина може вибирати музику залежно від свого настрою або бажаного впливу на психоемоційний стан. Вплив музики на психоемоційний стан може бути дуже індивідуальним, і люди можуть по-різному реагувати на кожен жанр. Тому важливо пам'ятати, що те, що працює для однієї людини, не обов'язково буде ефективним для іншої.
Провівши сегментацію на основі кількості годин музики, що прослуховується в день, можна побачити на візуалізації, що навіть при прослуховуванні до 2 годин на день у людей відчувається уже позитивний ефект. 
Також на дашборді можна переглянути візуалізацію середнього рівня психоемоційного стану в розрізі ступеня впливу. Як бачимо, у людей, які відчувають погіршення від прослуховування музики,  спостерігається високий рівень тривожності та депресії (21,6 бал), тому для цієї групи людей першою лінією лікування, все ж таки має бути медикаментозна підтримка. Люди із середнім рівнем розладу (17,4) відчувають значуще покращення.
Також на дашборді, окремо виведений графік сегментації на основі ступеню порушення і можна дійти до висновку що в кожній з груп - відсутність або легкий розлад, середній ступінь або важкий ступінь, спостерігається велика кількість людей, що відчувають покращення, після прослуховування музики.


6. Висновки та рекомендації:

1.	Загальний позитивний ефект: Більшість людей із вибірки (542 особи із 728 чоловік ) відчувають позитивний ефект від прослуховування музики, що вказує на те, що музика може бути корисною для психічного здоров'я.
2.	Негативний вплив на невелику кількість людей: Тільки невелика кількість людей (17 осіб) відчувають погіршення свого стану від прослуховування музики. Ці люди мають високий рівень тривожності та депресії, тому медикаментозне лікування може бути необхідним для них як перша лінія лікування.
3.	Вплив різних музичних жанрів: Популярність різних музичних жанрів (Rock, Pop, Metal, Classic) серед респондентів свідчить про різні уподобання. Враховуючи різні уподобання людей, неможливо однозначно визначити, який музичний жанр найкраще впливає на емоційний стан.
4.	Слабкий зв'язок між годинами прослуховування та рівнем психоемоційного стану: Коефіцієнт кореляції між годинами прослуховування музики та рівнем психоемоційного стану є низьким (0.15), що вказує на слабкий або відсутній зв'язок між цими двома змінними.
5.	Позитивний ефект при мінімальному прослуховуванні: Навіть при прослуховуванні до 2 годин на день спостерігається позитивний ефект, що свідчить про те, що навіть невелике прослуховування музики може покращити психоемоційний стан.
Рекомендації:
1.	Подальше вивчення: Рекомендується провести подальші дослідження, щоб краще зрозуміти, які аспекти музики можуть мати найбільший вплив на різні групи населення з різними рівнями психічного здоров'я.
2.	Індивідуальний підхід: Оскільки різні люди мають різні вподобання щодо музичних жанрів та різний психоемоційний стан, рекомендується розробляти індивідуальні рекомендації щодо прослуховування музики, враховуючи уподобання та особливості кожної людини.
3.	Музична терапія: Враховуючи позитивний вплив музики, рекомендується розглянути можливість використання музичної терапії як доповнення до інших методів лікування психічних розладів, особливо для тих, хто відчуває помірний рівень розладів.
4.	Збалансоване прослуховування: Враховуючи низький коефіцієнт кореляції між годинами прослуховування та психоемоційним станом, рекомендується збалансувати прослуховування музики та не збільшувати його безконтрольно.
5.	Дослідження для підтримки специфічних груп: Зосередити додаткові дослідження на підтримці тих людей, які відчувають негативний вплив музики, для розробки спеціалізованих рекомендацій та підтримки.

7. Документація:

1.	Файл - Music_dataset.xlsx - що містить датасет, проведену сегментацію та зведені таблиці, регресійний аналіз.
2.	Посилання на Tableau Public - де містяться візуалізації та дашборд.
3.	Файл Python, де був проведений кореляційний аналіз та його візуалізація.


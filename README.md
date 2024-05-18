# example_project

Приклад простого проекта на Python.


Структура:

- [config](./config/) -- папка з текстовими конфігураційними файлами. Зазвичай констант так багато, що їх виносять окремо. Якщо програма підтримує вкладку 'Налаштування', то, скоріш за все, налаштування будуть змінювати конфігураційні файли;
- [docs](./docs/) -- папка з документацією. У найпростішому вигляді це просто згенерована html сторінка, куди підтягується вся документація з класів, функцій, модулів, яку ви пишете в потрійних лапках впродовж розробки; Робиться це автоматично, наприклад за допомогою [sphinx](https://www.sphinx-doc.org/en/master/)
- [src](./src) -- папка з власне кодом. Може називатись інакше, якщо ви розробляєте бібліотеку наприклад, яку потім будуть імпортувати;
- [tests](./tests/) -- папка з тестами. Кожен тест -- це функція, яка називається `test_<something>`, де `<something>` означає конкретну частину коду, яку ви тестуєте. Ці тести потім автоматично проганяються наприклад модулем [pytest](https://pypi.org/project/pytest/)
- [LICENSE](./LICENSE) -- ліцензія на використання вашого коду. Просто щоб було
- [requirements.txt](./requirements.txt) -- тут описані всі бібліотеки, які ви використовуєте в своєму коді.
- [setup.py](./setup.py) -- файл, в якому описується порядок встановлення вашого коду

-----------

Розробку на Python зазвичай ведуть, використовуючи віртуальне середовище [venv](https://docs.python.org/3/library/venv.html). Це, по суті, повна копія необхідної версії інтерпретатора Python з усіма бібліотеками, які вам треба.

Щоб створити середовище, необхідно в консолі перейти в директорію з вашим проектом і запустити
```
$ python -m venv ./venv
```

Тоді з'явиться папка `venv`, де буде зберігатись повна копія Python. Щоб можна було його запускати, необхідно активувати віртуальне середовище:

1. На Windows:
```
$ .\venv\Scripts\activate
```
2. На Linux / MacOS:
```
$ source venv/bin/activate
```

Після виконання цієї команди з'явиться помітка `(venv)` зліва в консолі. Приклад:

```
[davendiy@davendiy ~/Documents/work/teaching/example_project]$ which python
/usr/bin/python
[davendiy@davendiy ~/Documents/work/teaching/example_project]$ source venv/bin/activate
(venv) [davendiy@davendiy ~/Documents/work/teaching/example_project]$ which python
/home/davendiy/Documents/work/teaching/example_project/venv/bin/python
```

Тобто коли ви будете виконувати команду `python`, то буде викликатись не глобальний інтерпретатор `/usr/bin/python`, а локальний у папці `venv`. Так само працюватиме `pip`. Тепер можна встановити бібліотеки з `requirements.txt`:

```
(venv) [davendiy@davendiy ~/Documents/work/teaching/example_project]$ pip install -r requirements.txt
```

Нарешті, щоб деактивувати середовище, необхідно просто виконати команду
```
$ deactivate
```


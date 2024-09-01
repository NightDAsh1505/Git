# repo1
"Вивчення Git"
Мета: Опанувати базові команди та принципи роботи з системою контролю версій Git, шляхом проходження курсу на githowto.com.

1. Найперше, що повинно бути виконано це декілька команд, щоб Git дізнався ім'я та електронну пошту. Ці дані використовуються для підпису змін, що дозволить відстежувати, хто і коли зробив зміни в файлі.

![1.1](screens1/1.1.jpg)

Перший рядок про ім’я.

Другий рядок про пошту.

Третій рядок - налаштовання початкової гілки за замовчуванням, в цьому випадку це main.

Четвертий рядок - забезпечує автоматичну конвертацію кінцівок рядків між форматами CRLF і LF під час коміту і checkout, щоб зробити їх однорідними у репозиторії, особливо у крос-платформних проєктах.

П’ятий рядок - встановлює Git на попередження про потенційні проблеми з кінцівками рядків (змішані кінцівки), що може допомогти уникнути проблем з файлом у репозиторії.

Ці конфігурації допомагають забезпечити узгодженість форматів кінцівок рядків у репозиторії та попередити можливі проблеми під час роботи з файлами на різних операційних системах.

![1.2](screens1/1.2.jpg)

Команда cat .gitconfig використовується для виведення вмісту файлу .gitconfig.

2. Створення проєкту

Для початку створюємо порожню піддиректорію work:

![2.1](screens1/2.1.jpg)

потім переходимо до неї: 

![2.2](screens1/2.2.jpg)

та створюємо файл hello.html:

![2.3](screens1/2.3.jpg)

Відкриваємо файл у редакторі nano:

![2.4](screens1/2.4.jpg)

І вводимо вміст «Hello, World».

Наразі є директорія з одним файлом. Для того щоб створити Git-репозиторій з цієї директорії, слід виконати команду git init:

![2.5](screens1/2.5.jpg)

Повідомлення каже про успішне створення Git-репозиторію.

Далі додаємо в репозитарій сторінку «hello.html»:

![2.6](screens1/2.6.jpg)

Потім створюємо коміт, -m дозволяє вказати повідомлення коміту — "Initial commit":

![2.7](screens1/2.7.jpg)

Слідом випливає повідомлення:
main: назва гілки. За замовчуванням, перша гілка у Git називається main.

(root-commit): вказує на те, що цей коміт є кореневим комітом (root commit), тобто першим комітом в історії цього репозиторію.

с61е77е:  перші сім символів хешу коміту (унікальний ідентифікатор коміту).

1 file changed: Вказує, що один файл (hello.html) був змінений або доданий.

3. Перевірка стану

Щоб дізнатися поточний стан репозиторія потрібно використовувати команду git status:

![3.1](screens1/3.1.jpg)

Команда перевірки стану повідомила, що комітити нема чого. Це означає, що у репозиторії вже зберігається поточний стан робочих файлів, та нема жодних змін, які б могли очікувати на запис.

4. Внесення змін

Відкриваємо файл у редакторі nano:

![4.1](screens1/4.1.jpg)

І змінюємо вміст:

![4.2](screens1/4.2.jpg)

Перевіряємо стан:

![4.3](screens1/4.3.jpg)

Файл було змінено, але ці зміни ще не зафіксовано у репозиторії.

5. Індексація змін

Наступним кроком буде дати команду Git проіндексувати зміни і слідом перевірити стан:

![5.1](screens1/5.1.jpg)

Повідомлення нам переказує, що зміни файлу hello.html було проіндексовано. Тобто Git знає про зміни.

7. Коміт змін

Тепер зробімо коміт того, що проіндексували у репозиторій.

Вводимо команду git commit, але без –m як це було раніше. Тоді нас переносить у редактор:

![7.1](screens1/7.1.jpg)

У першому рядку вводимо коментар Added h1 tag. Зберігаємо і виходимо:

![7.2](screens1/7.2.jpg)
![7.3](screens1/7.3.jpg)

Далі перевіряємо стан:

![7.4](screens1/7.4.jpg)

Бачимо що директорія чиста.

8. Зміни, а не файли

Знову змінюємо вміст файлу:

![8.2](screens1/8.2.jpg)

Тепер додаємо ці зміни в індекс Git:

![8.3](screens1/8.3.jpg)

І знову змінюємо файл, додаючи заголовок:

![8.4](screens1/8.4.jpg)

Перевіряємо статус:

![8.5](screens1/8.5.jpg)

Повідомлення показує що файл згадано двічі. Перша зміна проіндексована і готова до коміту. Друга зміна (де додали заголовки) є непроіндексована.

Якби зараз було зроблено коміт, заголовки не було б збережено у репозиторій. Це можна перевірити.

Робимо коміт проіндексованих змін і ще раз перевіряємо стан:

![8.6](screens1/8.6.jpg)

Команда статусу повідомляє, що у файлі досі є незбережені зміни.

Додаємо другу зміну в індекс (перший рядок означає що було використано поточну директорію) і знову перевіряємо стан:

![8.7](screens1/8.7.jpg)

Тепер ми бачимо що другу зміну було проіндексовано й приготовлено до коміту.
Тому далі робимо коміт цієї ж другої зміни:

![8.8](screens1/8.8.jpg)








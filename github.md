# Как настроить github

C августа 2021 года в github'е **запретили** авторизацию по паролю...

[<img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.pinimg.com%2F736x%2F3e%2Fa2%2F82%2F3ea282af3ee9103ba087e5b6795d1e5f.jpg&f=1&nofb=1" alt="my github is no probalo! | Meme faces, Funny reaction ..." style="zoom:25%;" />](https://i.pinimg.com/736x/3e/a2/82/3ea282af3ee9103ba087e5b6795d1e5f.jpg)

Авторизация теперь доступна только через Токен и SSH.

#### Как настроить SSH

###### *1 - Создание ключа*

Для начала нужно создать SSH ключ:

```bash
cd ~/.ssh/ && ssh-keygen -t rsa -b 4096 -C "email@example.com"
```

Далее ssh-keygen запросит:

- Имя файла: `Enter file in which to save the key (/home/schkn/.ssh/id_rsa):` 
- Пароль: `Enter passphrase (empty for no passphrase):` 
- Повторить пароль: `Enter same passphrase again:`

Просто нажмите `Enter`  3 раза, если не знаете что делать.

После этого в директории ~/.ssh/  появится файлики id_rsa и id_rsa.pub (если вы не меняли имя файла). Нас интересует файлик .pub - это публичный ключ и его нужно будет указать в гитхабе.

Чтобы вывести id_rsa.pub выпоните `cat is_rsa.pub`

###### *2 - Добавление ключа в github*

Копируем **публичный** ключ полученый на шаге 1.

На гитхабе переходим в **настройки** вашего аккаунта:

![Screenshot 2021-09-27 at 12.55.19](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 12.55.19.png)

Переходим в раздел **SSH and GCP keys**

![Screenshot 2021-09-27 at 12.59.46](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 12.59.46.png)

Нажмите кнопку **New SSH key**

![Screenshot 2021-09-27 at 13.01.47](/Users/ext.evikhrev/Desktop/Screenshot 2021-09-27 at 13.01.47.png)

Введите разумное название ключа и вставьте скопированный ключ.

Нажмите **Add SSH key**

**SSH ключ добавлен**

###### Внимание!!

SSH ключ будет работать только в репозитория клонированных через SSH:<img src="/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 13.04.14.png" alt="Screenshot 2021-09-27 at 13.04.14" style="zoom:50%;" />

Чтобы уже существующий локальный репозиторий работал через SSH можно использовать комманду:

```
git remote set-url origin <ssh-url>
```

Где shh-url копируется в меню клонирования во вкладке SSH.

**Лучше использовать авторизацию по SSH**, но если всё-таки хочется...

#### Как создать и использовать Токен

###### *1 - Создание токена*

Из меню настроек переходим в **Developer settings**

![Screenshot 2021-09-27 at 13.13.12](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 13.13.12.png)

Далее переходим к вкладке  **Personal access tokens**

![Screenshot 2021-09-27 at 13.14.47](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 13.14.47.png)

Жмём **Generate new token**

![Screenshot 2021-09-27 at 13.16.41](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 13.16.41.png)

Прописываем название токена и ставим галочку как на картинке. Можно поменять **Expiration**, чтобы не нужно было генерировать новый токен каждый месяц.

Токен сгенирирован.

![Screenshot 2021-09-27 at 13.18.56](/Users/ext.evikhrev/Library/Application Support/typora-user-images/Screenshot 2021-09-27 at 13.18.56.png)

Скопируйте его и используйте как пароль в локальных репозиториях с https remote'ом.

Этот способ **значительно** **менее безопасный**

Можете не пытаться меня взломать, этот токен я удалил :)
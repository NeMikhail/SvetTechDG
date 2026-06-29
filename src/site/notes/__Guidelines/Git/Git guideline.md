---
{"dg-publish":true,"permalink":"/guidelines/git/git-guideline/","dg-note-properties":{"tags":null}}
---

## 1. Установка Git на компьютер

<details> <summary>🎬 Видео-инструкция к этому этапу</summary> <br> <video src="Videofiles/GitGuideline/GitGuideline_Step_1.mp4" controls width="100%"></video> </details>

- Скачать Git с официального сайта: https://git-scm.com/downloads.
- Установить Git с настройками по умолчанию.
- После установки открыть терминал и проверить версию:

```bash
git --version
```

- Настроить имя пользователя и email, которые будут отображаться в коммитах:

```bash
git config --global user.name "Name Surname"
git config --global user.email "email@example.com"
```

- Проверить настройки:

```bash
git config --global --list
```

## 2. Генерация SSH-ключа

<details> <summary>🎬 Видео-инструкция к этому этапу</summary> <br> <video src="Videofiles/GitGuideline/GitGuideline_Step_2.mp4" controls width="100%"></video> </details>

- Подробная инструкция вынесена в отдельный guideline: [[__Guidelines/Git/Генерация SSH ключа\|Генерация SSH ключа]].
- После генерации ключа нужно добавить публичный ключ в GitLab.

## 3. Регистрация в GitLab и двухфакторная аутентификация

- Зарегистрироваться в GitLab или войти в выданный аккаунт.
- Проверить, что в профиле указан рабочий email.
- Включить двухфакторную аутентификацию по инструкции [[__Guidelines/Git/Двухфакторная аутентификация GitLab\|Двухфакторная аутентификация GitLab]].
- Сохранить backup codes в надежном месте.
- Убедиться, что есть доступ к репозиторию проекта.

## 4. Добавление SSH-ключа в GitLab

<details> <summary>🎬 Видео-инструкция к этому этапу</summary> <br> <video src="Videofiles/GitGuideline/GitGuideline_Step_4.mp4" controls width="100%"></video> </details>

- Открыть GitLab.
- Перейти в профиль пользователя.
- Открыть раздел SSH Keys.
- Вставить публичный ключ из файла `id_ed25519.pub` или другого файла, созданного по инструкции.
- Указать понятное название ключа, например `Work PC` или `Home Laptop`.
- Сохранить ключ.
- Проверить подключение:

```bash
ssh -T git@gitlab-games.elementsoftware.ru
```

- Если GitLab используется на собственном домене, заменить `gitlab.com` на домен проекта.

## 5. Выкачка проекта

<details> <summary>🎬 Видео-инструкция к этому этапу</summary> <br> <video src="Videofiles/GitGuideline/GitGuideline_Step_5.mp4" controls width="100%"></video> </details>

- Открыть страницу репозитория в GitLab.
- Скопировать SSH-ссылку на репозиторий.
- В терминале перейти в папку, где должен лежать проект.
- Выполнить клонирование:

```bash
git clone "ssh://git@gitlab-games.elementsoftware.ru:2222/svet_mmorpg/svet_mmo.git"
```

- Открыть папку проекта.
- Проверить текущую ветку:

```bash
git branch
```

- Обновить проект перед началом работы:

```bash
git pull
```

## 6. Базовый рабочий процесс

- Перед началом задачи обновить основную ветку.
- Создать отдельную ветку под задачу.
- Название ветки должно соответствовать [[__Conventions/1. Git convention\|1. Git convention]].
- Работать маленькими логическими изменениями.
- Перед коммитом проверить список измененных файлов.
- Не добавлять в коммит временные файлы, локальные настройки IDE и лишние ассеты.
- Делать коммит с коротким английским описанием изменения.
- Перед отправкой убедиться, что проект открывается и не содержит очевидных ошибок.
- Отправить ветку в удаленный репозиторий:

## 7. Merge request

- Сделать Rebase целевой ветки перед Merge.
- Создать pull request из рабочей ветки в целевую ветку проекта.
- В описании указать, что было сделано.
- Если есть номер задачи, добавить ссылку или номер задачи.
- Если есть риски или незавершенные места, явно написать об этом.
- После правок по ревью обновить тот же pull request, а не создавать новый.

## 8. Рекомендованный инструмент

- Рекомендованный инструмент для работы с Git: Fork.
- Подробная инструкция: [[__Guidelines/Git/Fork Git client guideline\|Fork Git client guideline]].

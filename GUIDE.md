# 🎨 Как прокачать GitHub-профиль Zennixxx

## 1. Что сейчас не так с профилем

| Что есть сейчас | Что улучшить |
|---|---|
| Нет профильного README | Сделать репозиторий `Zennixxx/Zennixxx` с README.md (главное улучшение) |
| Пустое Bio, Location, ссылка на сайт | Заполнить в **Settings → Profile** |
| 2 репозитория без описания | Добавить описание, topics и ссылку на демо |
| Ничего не закреплено | Закрепить (Pin) лучшие проекты |
| Нет ссылки на Upwork | Бейдж в README + ссылка в поле Website |

---

## 2. Создаём профильный README (5 минут)

1. Откройте https://github.com/new
2. **Repository name**: `Zennixxx` — точно как ваш логин, с учётом регистра.
   GitHub напишет: *"Zennixxx/Zennixxx is a ✨special✨ repository"*.
3. Сделайте его **Public**, поставьте галочку **Add a README file** → **Create repository**.
4. Залейте файлы из этой папки:

```bash
cd ~/Programming/Antigarvity/github-customizer
git init
git add .
git commit -m "feat: profile README"
git branch -M main
git remote add origin https://github.com/Zennixxx/Zennixxx.git
git push -u origin main --force   # --force перезапишет README, созданный GitHub'ом
```

Структура:
```
README.md                      ← сам профиль
.github/workflows/snake.yml    ← генерирует анимацию змейки
```

---

## 3. Что обязательно поменять в README.md

Найдите и замените заглушки:

| Заглушка | На что заменить |
|---|---|
| `YOUR_UPWORK_ID` (2 места) | Ваш ID из ссылки Upwork. Откройте свой профиль Upwork → ссылка вида `https://www.upwork.com/freelancers/~01abc123...` — скопируйте целиком |
| `your@email.com` | Ваша почта (или удалите бейдж) |
| `YOUR_TELEGRAM` | Ваш ник в Telegram (или удалите бейдж) |
| Текст в *About me* | Своё описание |
| Иконки в *Tech Stack* | Свой стек — список доступных иконок: https://skillicons.dev (например `python,vue,angular,firebase,aws`) |
| Строки в Typing SVG (`lines=...`) | Свои фразы, пробел = `+`, разделитель строк = `;` |

---

## 4. Включаем анимацию змейки 🐍

1. В репозитории `Zennixxx/Zennixxx` → **Settings → Actions → General**
2. В разделе **Workflow permissions** выберите **Read and write permissions** → **Save**
3. Вкладка **Actions** → *Generate snake animation* → **Run workflow**
4. Через ~1 минуту появится ветка `output` с файлом `github-snake-dark.svg` — змейка появится в профиле.
   Дальше она обновляется сама каждые 12 часов.

---

## 5. Статистика — как работает и как сделать надёжной

Все карточки — это картинки, которые генерируют внешние сервисы по вашему логину:

| Блок | Сервис |
|---|---|
| Stats + Top Languages + Pinned cards | github-readme-stats |
| Streak (серия дней) | streak-stats.demolab.com |
| Activity graph | github-readme-activity-graph |
| Profile views | komarev.com |

Цвета подобраны под тёмную тему GitHub: фон `#0d1117` (как у самого GitHub), акцент — фиолетовый `#a371f7`, текст `#c9d1d9`.
Хотите другой акцент — замените `a371f7` во всём файле, например на `58a6ff` (синий) или `3fb950` (зелёный).

### ⚠️ Если карточки статистики не грузятся
Публичный `github-readme-stats.vercel.app` иногда упирается в лимиты GitHub API и показывает ошибку. Надёжное решение — **свой бесплатный инстанс на Vercel**:

1. Создайте токен: https://github.com/settings/tokens → **Generate new token (classic)**, отметьте `repo` и `read:user`, скопируйте.
2. Сделайте форк: https://github.com/anuraghazra/github-readme-stats → **Fork**.
3. Зайдите на https://vercel.com → войдите через GitHub → **Add New → Project** → выберите форк.
4. В **Environment Variables** добавьте `PAT_1` = ваш токен → **Deploy**.
5. Получите адрес вида `https://github-readme-stats-xxx.vercel.app` и замените в README все
   `github-readme-stats.vercel.app` на свой домен.

Бонус: со своим токеном учитываются и **приватные** коммиты (`count_private=true`).

### Почему статистика может казаться маленькой
- Коммиты считаются, только если email в git совпадает с email на GitHub:
  `git config --global user.email` → должен быть добавлен в https://github.com/settings/emails
- Включите показ приватной активности: **Settings → Public profile → Contributions & activity → Include private contributions on my profile**.
- Карточки кэшируются на несколько часов — изменения видны не сразу.

---

## 6. Настройки профиля (Settings → Public profile)

- **Name**: Pavel
- **Bio**: например `Full-Stack TypeScript Developer · React / Node.js · Open for freelance`
- **URL / Website**: ссылка на Upwork — она будет видна прямо под аватаркой
- **Social accounts**: Telegram, LinkedIn
- **Location**, **Available for hire** ✅
- Аватар: нормальное фото или аккуратный аватар — заметно повышает доверие клиентов с Upwork

---

## 7. Оформление репозиториев

Для каждого проекта (`AIEditor`, `minesweeper-online`):
1. Справа у **About** нажмите ⚙️ → добавьте описание, ссылку на демо (Vercel/Netlify/GitHub Pages) и topics (`typescript`, `react`, `ai` …).
2. Добавьте в README проекта скриншот/GIF, список фич и инструкцию запуска.
3. На главной профиля → **Customize your pins** → закрепите лучшие проекты.

Для клиентов с Upwork живое демо + скриншот важнее, чем количество коммитов.

---

## 8. Чек-лист

- [ ] Создан репозиторий `Zennixxx/Zennixxx` и запушены файлы
- [ ] Заменены `YOUR_UPWORK_ID`, email, Telegram
- [ ] Включены Read/Write permissions и запущен workflow змейки
- [ ] Заполнены Bio, Website (Upwork), аватар
- [ ] Включены приватные контрибуции
- [ ] У проектов есть описание, topics, демо, закреплены
- [ ] (Опционально) Развёрнут свой github-readme-stats на Vercel

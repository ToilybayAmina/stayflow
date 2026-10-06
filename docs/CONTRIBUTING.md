# Жобаға үлес қосу ережелері

## 1. Branch атау келісімі

### Формат

```
<тип>/<issue-id>-<қысқа-сипаттама>
```

### Типтер

| Тип | Қашан қолданылады | Мысал |
|---|---|---|
| `feature/` | Жаңа функция | `feature/ZAY-1-booking-form` |
| `bugfix/` | Қатені түзету | `bugfix/ZAY-5-queue-sorting` |
| `ai/` | AI-ға қатысты | `ai/ZAY-3-no-show-model` |
| `docs/` | Құжаттама | `docs/ZAY-20-adr-002` |
| `infra/` | Инфрақұрылым | `infra/ZAY-9-ci-pipeline` |
| `hotfix/` | Шұғыл түзету | `hotfix/ZAY-15-critical-bug` |

### Ережелер

- Атауы **ағылшын тілінде**, кіші әріптермен
- Сөздер **сызықшамен** (`-`) бөлінеді
- Issue ID **міндетті** (мысалы, `ZAY-1`)
- Максимум **50 символ**

### Мысалдар

✅ **Дұрыс:**
```
feature/ZAY-1-booking-form
bugfix/ZAY-5-queue-sorting
ai/ZAY-3-no-show-model
docs/ZAY-20-adr-002
```

❌ **Қате:**
```
my-branch
feature/booking
ZAY-1
new-feature-test
```

---

## 2. Commit келісімі (Conventional Commits)

### Формат

```
<тип>(<аясы>): <сипаттама>

<толық сипаттама (міндетті емес)>

<footer (міндетті емес)>
```

### Типтер

| Тип | Қашан қолданылады | Мысал |
|---|---|---|
| `feat` | Жаңа функция | `feat(booking): add online booking form` |
| `fix` | Қатені түзету | `fix(admin): correct room status update` |
| `docs` | Құжаттама | `docs(adr): add ADR-002 for AI model` |
| `style` | Форматтау (логика өзгермейді) | `style(booking): format code` |
| `refactor` | Рефакторинг | `refactor(api): simplify booking endpoint` |
| `test` | Тестілер | `test(ai): add no-show model tests` |
| `chore` | Қосымша жұмыс | `chore(deps): update dependencies` |
| `ai` | AI-ға қатысты | `ai(model): improve F1 to 0.78` |
| `infra` | Инфрақұрылым | `infra(ci): add GitHub Actions workflow` |

### Аясы (scope) — қай бөлікке қатысты

| Аясы | Қайда |
|---|---|
| `booking` | Брондау модулі |
| `admin` | Әкімші панелі |
| `ai` | AI модулі |
| `api` | Backend API |
| `ui` | Frontend |
| `db` | Дерекқор |
| `ci` | CI/CD |
| `docs` | Құжаттама |

### Ережелер

- Сипаттама **ағылшын тілінде**, кіші әріптермен
- Сипаттама **қысқа** (максимум 72 символ)
- Етістік **бұйрық райында** (add, fix, update — added, fixed емес)
- Нүкте **қойылмайды** соңында

### Мысалдар

✅ **Дұрыс:**
```
feat(booking): add online booking form
fix(admin): correct room status update
ai(model): improve no-show prediction F1 to 0.78
docs(adr): add ADR-002 for AI model choice
test(ai): add unit tests for no-show model
infra(ci): add GitHub Actions workflow
```

❌ **Қате:**
```
Added new feature
fix bug
update
ZAY-1
WIP
```

### Толық мысал (footer-мен)

```
feat(booking): add online booking form

Формада күн, қонақ саны, бөлме түрі бар.
Валидация Pydantic арқылы жасалды.

Closes #1
```

---

## 3. Pull Request ережелері

### Формат

```
<тип>: <қысқа сипаттама>

## Не өзгерді
- ...

## Қалай тексеру керек
1. ...

## Скриншоттар (егер UI болса)
...

Closes #<issue-id>
```

### Ережелер

1. **Әр PR — бір тапсырма** (бір Issue)
2. **Кемінде 1 review** (басқа команда мүшесінен)
3. **CI өтуі керек** (барлық тестілер жасыл)
4. **Конфликт жоқ** (main-мен)
5. **Тақырып** Conventional Commits форматында

### Мысал PR

**Title:**
```
feat(booking): add online booking form
```

**Description:**
```markdown
## Не өзгерді
- Онлайн брондау формасы қосылды
- Валидация Pydantic арқылы
- Email растау жіберу

## Қалай тексеру керек
1. `/booking` бетін ашу
2. Форманы толтыру
3. «Отправить» басу
4. Email келуін тексеру

## Скриншоттар
![Форма](./screenshots/booking-form.png)

Closes #1
```

---

## 4. Код ревью ережелері

### Ревьюер не тексереді

- [ ] Код **оқылады** (анық атаулар, комментарийлер)
- [ ] **Тестілер** бар
- [ ] **CI** өтті
- [ ] **Құжаттама** жаңартылды (қажет болса)
- [ ] **Қауіпсіздік** мәселелері жоқ
- [ ] **Өнімділік** нашарлаған жоқ

### Ревьюер қалай жауап береді

| Белгі | Мағынасы |
|---|---|
| ✅ **LGTM** | Looks Good To Me — мақұлданды |
| 💬 **Comment** | Пікір, бірақ бөгет емес |
| 🔧 **Request changes** | Өзгерту керек |
| ❓ **Question** | Сұрақ |

---

## 5. Merge ережелері

### Қашан merge жасауға болады

- ✅ Барлық тестілер өтті
- ✅ Кемінде 1 review мақұлданды
- ✅ CI жасыл
- ✅ Конфликт жоқ

### Merge түрлері

| Түр | Қашан |
|---|---|
| **Squash and merge** | Көп commit → 1 commit (ұсынылады) |
| **Rebase and merge** | Таза тарих |
| **Merge commit** | Барлық commit сақталады |

**Ұсыныс:** `Squash and merge` — тарих таза болады.

---

## 6. Мысал жұмыс процесі

### 1. Issue алу
```
ZAY-1: Онлайн брондау формасы
```

### 2. Branch жасау
```bash
git checkout main
git pull origin main
git checkout -b feature/ZAY-1-booking-form
```

### 3. Жұмыс істеу
```bash
# Код жазу
git add .
git commit -m "feat(booking): add online booking form"
```

### 4. Push
```bash
git push origin feature/ZAY-1-booking-form
```

### 5. PR ашу
GitHub-та:
```
Title: feat(booking): add online booking form
Description: Closes #1
```

### 6. Review алу
Басқа команда мүшесі тексереді.

### 7. Merge
**Squash and merge** басыңыз.

### 8. Branch өшіру
```bash
git branch -d feature/ZAY-1-booking-form
```

---

## 7. Жиі кездесетін қателер

| Қате | Қалай түзету |
|---|---|
| Branch атауы дұрыс емес | `feature/ZAY-1-booking-form` |
| Commit хабары ағылшын емес | `feat(booking): add form` |
| PR үлкен (бірнеше тапсырма) | Бір PR = бір Issue |
| CI өтпейді | Тестілерді түзету |
| Review жоқ | Команда мүшесін шақыру |
| Конфликт бар | `git rebase main` |

---

## 8. Пайдалы командалар

```bash
# Branch тізімін көру
git branch -a

# Branch ауысу
git checkout feature/ZAY-1-booking-form

# Өзгерістерді көру
git status

# Commit жасау
git add .
git commit -m "feat(booking): add form"

# Push
git push origin feature/ZAY-1-booking-form

# Main-нен жаңарту
git checkout main
git pull origin main
git checkout feature/ZAY-1-booking-form
git rebase main
```

---

## 9. Байланыс

| Рөл | Аты | GitHub |
|---|---|---|
| PM | Тойлыбай Амина | @amina |
| Аналитик | Файзуллаев Серик | @serik |
| Әзірлеуші | Туленов Мухамедәли | @muhamedali |

---

*Соңғы жаңарту: 2026 жыл, 2-апта*

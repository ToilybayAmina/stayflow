# StayFlow

City Hotel үшін қонақ үй брондауын басқару және no-show болжау жүйесі.

## Мәселе

City Hotel-де 79,330 брондаудың 29,352-і (37.0%) жойылады.
Қонақ үй қай брондау жойылатынын алдын ала білмейді.

Себебі:
- Орташа lead time — 104 күн
- Брондаулардың 87%-ы депозитсіз
- Online TA арнасында no-show 42%

## Шешім

AI no-show болжау + біртұтас брондау жүйесі + әкімші панелі.

## Технологиялық стек

- **Backend:** Python 3.11 + FastAPI
- **Frontend:** React + Tailwind CSS
- **Database:** PostgreSQL 16 (Docker)
- **AI:** scikit-learn (Random Forest) + Ollama
- **CI/CD:** GitHub Actions
- **Monitoring:** Uptime Kuma + Grafana OSS

## Команда

- **Тойлыбай Амина** (Студент А) — PM + City Hotel менеджерімен байланыс
- **Файзуллаев Серик** (Студент Б) — аналитик + AI моделі
- **Туленов Мухамедәли** (Студент В) — әзірлеу + CI/CD + тестілеу

## Датасет

Hotel Booking Demand (Kaggle) — 79,330 City Hotel жазбасы

- 🔗 https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

## Құжаттама

- [ADR-001: Жеткізу моделі](docs/adr/ADR-001-delivery-model.md)
- [Талаптар](docs/requirements/)
- [Runbook](docs/runbook.md)

## Жоба мәртебесі

- [x] 1-апта: Жоба карточкасы
- [x] 2-апта: ADR-001 + GitHub жұмыс кеңістігі
- [ ] 3-апта: Бизнес-кейс + TCO/ROI
- [ ] 4-апта: Story map + НФТ
- [ ] 5-апта: WBS + RACI
- [ ] 6-апта: Монте-Карло
- [ ] 7-апта: RAID + STRIDE
- [ ] 8-апта: SoW + SLA + бюджет
- [ ] 9-апта: 2 спринт
- [ ] 10-апта: CI/CD + DORA
- [ ] 11-апта: Тестілеу + UAT
- [ ] 12-апта: AI-функция + eval
- [ ] 13-апта: PM AI-ассистенті
- [ ] 14-апта: WSJF + дашборд
- [ ] 15-апта: Қорғау + портфолио

## Лицензия

Оқу жобасы — 2026

# Marketplace Architecture (C4 + Docker)

## Что сделано
- Спроектирована архитектура маркетплейса (контейнерный уровень)
- Построена C4 Container диаграмма
- Поднят один сервис в Docker с health-check endpoint `/health` (200 OK)

## Архитектура (коротко)
Marketplace состоит из основных доменов:
- Users (покупатели/продавцы)
- Catalog (товары)
- Feed/Recommendations (персонализированная лента)
- Orders (оформление заказов)
- Payments (учет платежей + интеграция с провайдером)
- Notifications (уведомления о статусах)

Вход в систему через API Gateway. Интеграции с внешними системами: Payment Provider и Email/SMS/Push Provider.

## C4 Container diagram
Файл: `docs/c4-container.puml`

## Docker service
Поднят сервис: `notification-service`

### Run
```bash
cd services/notification-service
docker compose up --build
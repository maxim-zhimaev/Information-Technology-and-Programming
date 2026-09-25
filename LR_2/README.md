Схемы для лабораторной работы №2

1. Внешняя структура: Макет главной страницы

```mermaid
flowchart TB
    subgraph Header [Шапка сайта]
        direction LR
        L[Логотип] --- M[Меню: Главная | Каталог | Контакты] --- T[Телефон]
    end

    subgraph Main [Основной контент]
        direction TB
        B[Баннер с текущей акцией]
        P[Блок преимуществ: Быстрая печать | Доставка курьером]
        
        subgraph Services [Популярные услуги]
            direction LR
            S1[Визитки] --- S2[Буклеты] --- S3[Баннеры]
        end
        
        B --> P --> Services
    end

    subgraph Footer [Подвал сайта]
        direction LR
        C[Контакты] --- Soc[Социальные сети] --- Copy[© 2026 Копирайт]
    end

    Header --> Main --> Footer

    classDef section fill:#f9f9f9,stroke:#333,stroke-width:2px;
    class Header,Main,Footer section;

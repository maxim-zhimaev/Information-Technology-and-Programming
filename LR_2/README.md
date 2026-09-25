Markdown

### 1. Внешняя структура: Макет главной страницы

```mermaid
flowchart TB
    subgraph Header [Шапка сайта]
        direction LR
        L[Логотип] --- M["Меню: Главная | Каталог | Контакты"] --- T[Телефон]
    end

    subgraph Main [Основной контент]
        direction TB
        B[Баннер с текущей акцией]
        P["Блок преимуществ: Быстрая печать | Доставка курьером"]
        
        subgraph Services [Популярные услуги]
            direction LR
            S1[Визитки] --- S2[Буклеты] --- S3[Баннеры]
        end
        
        B --> P --> Services
    end

    subgraph Footer [Подвал сайта]
        direction LR
        C[Контакты] --- Soc[Социальные сети] --- Copy["© 2026 Копирайт"]
    end

    Header --> Main --> Footer

    classDef section fill:#f9f9f9,stroke:#333,stroke-width:2px;
    class Header,Main,Footer section;

2. Внешняя структура: Макет страницы услуги (Визитки)
Фрагмент кода

flowchart TB
    subgraph Header [Шапка сайта]
        direction LR
        L[Логотип] --- M["Меню: Главная | Каталог | Контакты"] --- T[Телефон]
    end

    subgraph Main [Основной контент]
        direction TB
        Nav["Навигация: Главная > Каталог > Визитки"]
        Title([ЗАГОЛОВОК: ВИЗИТКИ])
        
        subgraph Calc [Интерактивный калькулятор]
            direction TB
            C1[Выбор тиража]
            C2[Выбор бумаги]
            C3[Итого: XXX руб.]
            
            C1 --> C2 --> C3
        end
        
        Btn[[КНОПКА: ЗАКАЗАТЬ]]
        
        Nav --> Title --> Calc --> Btn
    end

    subgraph Footer [Подвал сайта]
        direction LR
        C[Контакты] --- Soc[Социальные сети] --- Copy["© 2026 Копирайт"]
    end

    Header --> Main --> Footer

    classDef section fill:#f9f9f9,stroke:#333,stroke-width:2px;
    class Header,Main,Footer section;

3. Внутренняя структура: Иерархия (дерево) страниц
Фрагмент кода

flowchart TD
    Index((Главная страница))
    
    Cat[Каталог]
    Deliv[Доставка]
    Cont[Контакты]
    
    Index --> Cat
    Index --> Deliv
    Index --> Cont
    
    Vizit[Визитки]
    Book[Буклеты]
    Ban[Баннеры]
    
    Cat --> Vizit
    Cat --> Book
    Cat --> Ban
    
    Vizit2[Двусторонние визитки]
    
    Vizit --> Vizit2
    
    classDef main fill:#d4edda,stroke:#28a745,stroke-width:2px;
    classDef section fill:#cce5ff,stroke:#007bff,stroke-width:2px;
    classDef item fill:#f8d7da,stroke:#dc3545,stroke-width:2px;
    
    class Index main;
    class Cat,Deliv,Cont section;
    class Vizit,Book,Ban,Vizit2 item;

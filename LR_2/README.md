Схемы для лабораторной работы №2

1. Внешняя структура: Макет главной страницы

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


2. Внешняя структура: Макет страницы услуги (Визитки)

flowchart TB
    subgraph Header [Шапка сайта]
        direction LR
        L[Логотип] --- M[Меню: Главная | Каталог | Контакты] --- T[Телефон]
    end

    subgraph Main [Основной контент]
        direction TB
        Nav[Навигация: Главная > Каталог > Визитки]
        Title([ЗАГОЛОВОК: ВИЗИТКИ])
        
        subgraph Calc [Интерактивный калькулятор]
            direction TB
            C1[Выбор тиража]
            C2[Выбор типа бумаги]
            C3[[Итоговая стоимость: XXX руб.]]
            C1 --> C2 --> C3
        end
        
        Btn{КНОПКА: ЗАКАЗАТЬ}
        
        Nav --> Title --> Calc --> Btn
    end

    subgraph Footer [Подвал сайта]
        direction LR
        C[Контакты] --- Soc[Социальные сети] --- Copy[© 2026 Копирайт]
    end

    Header --> Main --> Footer
    
    classDef section fill:#f9f9f9,stroke:#333,stroke-width:2px;
    class Header,Main,Footer section;


3. Внутренняя структура: Иерархия страниц (Дерево сайта)

graph TD
    A([Главная страница]) --> B[Каталог]
    A --> C[Доставка]
    A --> D[Контакты]
    A --> E[О компании]
    
    B --> F[Визитки]
    B --> G[Буклеты]
    B --> H[Баннеры]
    
    F --> I[Двусторонние визитки]
    F --> J[Односторонние визитки]
    
    classDef main fill:#d4edda,stroke:#28a745,stroke-width:2px;
    classDef section fill:#cce5ff,stroke:#007bff,stroke-width:2px;
    classDef item fill:#fff3cd,stroke:#ffc107,stroke-width:2px;
    
    class A main;
    class B,C,D,E section;
    class F,G,H,I,J item;

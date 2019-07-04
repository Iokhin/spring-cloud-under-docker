Чтобы развернуть окружение облака:
    
    docker-compose up

Чтобы развернуть несколько экземпляров sencha-приложения в облаке:

    docker-compose up --scale sencha=3
    
Сервисы и порты:

    eureka: 8761
    zuul: 8080
    config: 8888
    sencha: не выставлен вовне (находится в сети Docker)
    postgresql: 5432
        user: root
        pass: root
        dbname: tm
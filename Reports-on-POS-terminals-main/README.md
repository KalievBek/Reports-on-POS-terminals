# Reports on POS Terminals

Сервис для обработки транзакций между банковскими счетами через POS-терминалы.

## Технологии

- Java (Spring Boot)
- Maven
- Lombok
- Log4j2
- JPA/Hibernate

## Функциональность

- Проверка баланса перед транзакцией
- Переводы между счетами одного банка (Bank A -> Bank A)
- Переводы между разными банками (Bank A -> Bank B)
- Транзакционная безопасность
- Обработка исключений (недостаточно средств, счёт не найден)
- Сохранение истории транзакций

## Основные классы

- PaymentSystem - проверка баланса счетов
- TransactionService - обработка транзакций
- ABankScoreRepository / BBankScoreRepository - репозитории банковских счетов
- TransactionRepository - репозиторий истории транзакций

## Логирование

При успешной транзакции выводится лог: "Transferring {сумма} from {номер} to {код устройства}"

## Исключения

- ScoreNotFoundException - счёт не найден
- BalanceNotEnoughException - недостаточно средств

## Запуск

1. Собрать проект: mvn clean install
2. Запустить приложение: mvn spring-boot:run

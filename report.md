# Отчёт о тестировании приложения "Money Transfer"

## Краткое описание

В IDEA создан новый проект Money Transfer, который производит расчёт суммы средств на счёте клиента. Приложение производит 2 операции: зачисление средст и списание средств.

## Описание тестов
Проведено позитивное, функциональное тестирование 2 функций: списание денежных средств и зачисление. 

## Результаты

1. 1 успешный/ 1 не успешный тест.
2. [ссылка на баг репорт](https://github.com/YuriKopshev/Money-taransfer/issues/1#issue-654041230)

## Общие рекомендации

Ошибака произощла по причине того , что переменная int, хранит хранит целое число от -2147483648 до 2147483647 и занимает 4 байта. 
При зачислении средств сумма отображается неккоретно, минусовое значение. Это происходит потому что в двоичном формате, первый бит заменяется на единицу,поэтому первый знак автоматически убирается и получается:
10000000000000000000000000000000, что эквивалентно значению -2147483647.
Рекомендуется использовать переменну long.

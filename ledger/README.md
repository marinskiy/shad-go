# ledger

Реализуйте объект для хранения банковских счетов. Требуемый интерфейс находится в `model.go`.

- Функция `New` должна создавать таблицу в базе данных.
- Метод `CreateAccount` должен создавать новый счёт с заданным `id`.
- Метод `GetBalance` должен возвращать текущий баланс.
- Метод `Deposit` должен зачислять деньги на счёт.
- Метод `Withdraw` должен снимать деньги со счёта.
  Если на счету не достаточно денег, метод должен возвращать ошибку `ledger.ErrNoMoney`.
- Метод `Transfer` должен переводить деньги со счёта `from` на счёт `to`.
  Если на счету `from` не достаточно денег, метод должен возвращать ошибку `ledger.ErrNoMoney`.

Все операции должны быть атомарными. Для реализации некоторых методов
вам потребуется использовать транзакции и row-level локи. Ваша реализация не должна создавать дедлоки на уровне базы данных.

Мы рекомендуем использовать функциональность `SELECT FOR UPDATE`.

Комментарии по запуску postgres смотрите в задаче [dao](../dao/).
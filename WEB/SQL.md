# Jazyk SQL

`Dialekt, standard, DML, DDL, DCL, TCL, INSERT, UPDATE, DELETE, CREATE, ALTER, DROP, GRANT, REVOKE, transakce`

## SQL

- `structured query language​`
- dotazovací jazyk​
- práce s daty v relačních databázích (tabulky)​
- dialekty
  - MySQL
  - MSSQL
  - SQL Server

## Standard

- udržuje a definuje ISO a ANSI​
- SQL 2016​
- syntaxe, datové typy, funkce jazyka

## DML

- `Data manipulation language`
- jazyk pro manipulování s daty​

### INSERT

- přidá položku do databáze

```SQL
INSERT INTO Zamestnanci (id, jmeno, prijmeni)​
VALUES (55, 'Jan', 'Novák');​
```

### UPDATE

- modifikace existujících záznamů v tabulce

```SQL
UPDATE table_name​
SET column1 = value1, column2 = value2, ...​
(WHERE condition);
```

### DELETE

- maže záznamy z tabulky​

```SQL
DELETE FROM table_name (WHERE condition);
```

## DDL

- `Data definition language​`
- definice struktury DB​

### CREATE

- vytvoří novou tabulku v databázi​

```SQL
CREATE TABLE Persons (​
    PersonID int,​
    LastName varchar(255),​
    FirstName varchar(255),​
    Address varchar(255),​
    City varchar(255)​
);
```

### ALTER

- příkaz se používá k přidání, odstranění nebo úpravě sloupců v existující tabulce

```SQL
ALTER TABLE Customers​
ADD Email varchar(255);
```

### DROP

- odstranění definice tabulky a všech dat, indexů, triggerů, omezení a specifikací oprávnění pro tuto tabulku

```SQL
DROP TABLE table_name; -- vymaže tabulku i obsah​
TRUNCATE TABLE table_name; -- vymaže obsah tabulky
```

## DCL

- `Data Control Language​`
- řízení přístupu k datům​

### GRANT

- poskytnutí oprávnění k tabulkám (SELECT, INSERT, UPDATE, DELETE)​

```SQL
GRANT privilege_name​
ON object_name​
TO {user_name |PUBLIC |role_name}​
[WITH GRANT OPTION];​
```

### REVOKE

- odebírá práva

```SQL
REVOKE privilege_name​
ON object_name​
FROM {user_name |PUBLIC |role_name};
```

## TCL

- `Transaction Control Language​`
- pro řízení transakcí​

### Transakce

- sekvence jednoho nebo více SQL dotazů, které jsou vykonány najednou​
- **BEGIN TRANSACTION**
  - začne novou transakci​
- **COMMIT**
  - uloží změny vytvořené během transakce​
- **ROLLBACK**
  - zvrátí všechny změny vytvořené během transakce do stavu před započetím transakce​

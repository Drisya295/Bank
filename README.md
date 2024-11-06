# Bank

Database script as below:

CREATE TABLE Accounts (
    AccountId NVARCHAR(50) PRIMARY KEY,
    Balance DECIMAL(18, 2)
);

CREATE TABLE Transactions (
    TransactionId NVARCHAR(50) PRIMARY KEY,
    AccountId NVARCHAR(50) FOREIGN KEY REFERENCES Accounts(AccountId),
    Date DATETIME,
    Type NVARCHAR(1),
    Amount DECIMAL(18, 2)
);

CREATE TABLE InterestRules (
    RuleId NVARCHAR(50) PRIMARY KEY,
    Date DATETIME,
    Rate DECIMAL(5, 2)
);

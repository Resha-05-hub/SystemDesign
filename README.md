Recurring Deposit (RD) Interest Calculator Project Objective

This is a console-based Java application that allows a bank clerk to compute the maturity amount for a Recurring Deposit (RD) account. It calculates:

Total amount deposited Total interest earned (quarterly compounding) Final maturity amount (Deposit + Interest)

About Recurring Deposit

A Recurring Deposit (RD) is a savings scheme where customers deposit a fixed monthly amount for a fixed tenure (5 or 10 years). Banks pay interest at a predetermined rate, compounded quarterly. This project simulates the process of calculating RD maturity.

System Design Package Structure com.wipro.bank.acc → Account related classes
com.wipro.bank.exception → Custom exceptions
com.wipro.bank.service → Validation & calculation services
com.wipro.bank.main → Main class to run application

Packages & Classes 1.com.wipro.bank.exception

BankValidationException Custom exception class toString() → "Invalid Data"

2.com.wipro.bank.acc

Account (Abstract Class) Variables: int tenure, float principal, float rateOfInterest Methods: setInterest(int age, String gender) → Sets rate based on gender & age calculateMaturityAmount(float totalDeposited, float interest) → Returns maturity amount abstract float calculateInterest() → Calculates interest abstract float calculateAmountDeposited() → Calculates total deposit RDAccount (Inherits Account) Constructor: RDAccount(int tenure, float principal) Implements: calculateAmountDeposited() → Returns Principal × Tenure × 12 calculateInterest() → Uses quarterly compounding formula

3.com.wipro.bank.service

BankService validateData(float principal, int tenure, int age, String gender) Validates inputs Rules: Principal ≥ 500 Tenure = 5 or 10 Gender = male/female Age between 1–100 Throws BankValidationException if invalid calculate(float principal, int tenure, int age, String gender) If valid → Creates RDAccount, sets interest, and calculates: Deposited Amount Interest Earned Maturity Amount

4.com.wipro.bank.main

MainClass Accepts user input Calls BankService.calculate() Prints results

Example Calculation

Principal = ₹1000/month Tenure = 5 years (60 months) Rate = 9.8%

Total Deposited = ₹60,000 Interest Earned ≈ ₹17,491.522 Maturity Amount = ₹77,491.52

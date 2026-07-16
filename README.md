# ATM Simulation System (C++)

A realistic, console-based ATM (Automated Teller Machine) simulator built in C++. The application interfaces directly with a structured flat-file client database to authenticate cardholders and perform real-time balance modifications, withdrawals, and deposits.

## 🚀 Key Features

### 1. Secure Client Login
* Authenticates clients using their **Account Number** and **PIN Code**[cite: 2].
* Validates credentials against the active text database (`Clients.txt`) prior to granting main menu access[cite: 2].

### 2. Quick Withdraw Menu
Allows users to quickly withdraw standard pre-set amounts:
* Preset options: **$20, $50, $100, $200, $400, $600, $800, $1000**[cite: 2].
* Automatically verifies if the chosen amount exceeds the client's current balance before processing[cite: 2].

### 3. Custom Normal Withdraw & Deposit
* **Custom Withdrawals:** Allows withdrawals of custom amounts, strictly validated to be in **multiples of $5** to simulate real physical ATM hardware[cite: 2].
* **Instant Deposits:** Allows secure, positive value deposits directly to the client's account balance[cite: 2].
* **Real-time Database Sync:** All successful transactions instantly rewrite and update the underlying database file, preventing balance discrepancies[cite: 2].

---

## 🛠️ Data Structures & File Layout

The system manages accounts using the following structured representation:

```cpp
struct sClient {
    string AccountNumber;
    string PinCode;
    string Name;
    string Phone;
    double AccountBalance;
    bool MarkForDelete = false;
};

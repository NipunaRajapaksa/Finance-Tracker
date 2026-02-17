# Finance-Tracker

A Python-based personal finance tracking application that helps you manage your income and expenses with both command-line and graphical user interfaces.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
  - [Command-Line Interface](#command-line-interface)
  - [Graphical User Interface](#graphical-user-interface)
  - [Bulk Transaction Import](#bulk-transaction-import)
- [File Structure](#file-structure)
- [Data Format](#data-format)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Add Transactions**: Record income and expense transactions with category, amount, date, and type
- **View Transactions**: Display all transactions in a sortable and searchable GUI table
- **Update Transactions**: Modify existing transaction details (amount, date, or status)
- **Delete Transactions**: Remove unwanted transactions from your records
- **Display Summary**: View total income, total expenses, and net profit/loss
- **Bulk Import**: Import multiple transactions from a text file at once
- **Search Functionality**: Search transactions by type, amount, date, or status
- **Sort Functionality**: Sort transactions by any column in the GUI
- **Data Persistence**: All transactions are saved in JSON format

## Prerequisites

- Python 3.x
- tkinter (usually comes pre-installed with Python)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/NipunaRajapaksa/Finance-Tracker.git
cd Finance-Tracker
```

2. Ensure you have Python 3 installed:
```bash
python --version
```

3. No additional packages need to be installed as the application uses Python's standard library (tkinter, json, datetime).

## Usage

### Command-Line Interface

Run the main application:
```bash
python Finance_tracker2.py
```

You'll be presented with a menu:
```
Personal Finance Tracker
1. Add Transaction
2. View Transactions
3. Update Transaction
4. Delete Transaction
5. Display Summary
6. Exit
```

#### Adding a Transaction

1. Select option `1` from the main menu
2. Choose whether to add bulk transactions or a single transaction
3. For single transaction, provide:
   - Category (e.g., "Salary", "Groceries", "Rent")
   - Amount (integer value)
   - Type (income or expense)
   - Date (YYYY/MM/DD format)

#### Viewing Transactions

1. Select option `2` from the main menu
2. A GUI window will open displaying all transactions in a table format
3. You can:
   - Search for specific transactions using the search bar
   - Sort by clicking on column headers
   - Refresh the view using the Refresh button

#### Updating Transactions

1. Select option `3` from the main menu
2. Choose the transaction category you want to update
3. Select the transaction group number
4. Choose which field to update (amount, date, or status)
5. Enter the new value

#### Deleting Transactions

1. Select option `4` from the main menu
2. Choose the transaction category
3. Select the transaction group number to delete
4. Choose whether to continue deleting more transactions

#### Displaying Summary

1. Select option `5` from the main menu
2. View total income, total expenses, and net profit/loss

### Graphical User Interface

You can also run the GUI directly:
```bash
python GUI.py
```

This will open a window displaying all transactions with the following features:
- **Sortable Columns**: Click on column headers to sort
- **Search Bar**: Search transactions by any field
- **Refresh Button**: Reload all transactions

### Bulk Transaction Import

To import multiple transactions at once:

1. Create a file named `bulk_transaction.txt` in the project directory
2. Format each transaction as: `category,amount,date,income/expense`
3. Example:
```
Salary,230000,2023/03/03,income
Groceries,150,2023/03/05,expense
Rent,50000,2023/03/01,expense
Utilities,5000,2023/03/10,expense
```
4. Select option `1` from the main menu
5. Choose "yes" when asked about bulk transactions
6. Transactions will be imported and the file will be cleared

## File Structure

```
Finance-Tracker/
│
├── Finance_tracker2.py      # Main application with CLI interface
├── GUI.py                    # GUI module for displaying transactions
├── transactions.json         # Data storage file (auto-generated)
├── bulk_transaction.txt      # File for bulk import (user-created)
└── README.md                 # This documentation file
```

## Data Format

Transactions are stored in `transactions.json` with the following structure:

```json
{
  "Category Name": [
    {
      "amount": 1000,
      "date": "2024-02-01",
      "status": "income"
    }
  ]
}
```

- **Category Name**: String key representing the transaction category
- **amount**: Integer value of the transaction
- **date**: String in YYYY-MM-DD or YYYY/MM/DD format
- **status**: Either "income" or "expense"

## Examples

### Example Transaction Flow

```
Enter your choice: 1
Do you want to enter bulk transaction:(yes/no) no
Category of the transaction: Freelance Work
Enter the amount: 15000
Type of transaction (Income or Expense): income
Enter the date YYYY/MM/DD: 2024/02/15
```

### Example Summary Output

```
Total Income is : 245000
Total Expense is : 55150
Your net income (profit) is : 189850
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.
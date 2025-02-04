import datetime

class ExpenseTracker:
    def __init__(self):
        self.expenses = []

    def add_expense(self, amount, description):
        expense = {
            'amount': amount,
            'description': description,
            'date': datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S')
        }
        self.expenses.append(expense)
        print(f"Added expense: {description} - {amount}")

    def view_expenses(self):
        if not self.expenses:
            print("No expenses recorded.")
            return
        
        print("Date and Time\t\t\tAmount\tDescription")
        for expense in self.expenses:
            print(f"{expense['date']}\t{expense['amount']}\t{expense['description']}")

    def calculate_total(self):
        total = sum(expense['amount'] for expense in self.expenses)
        print(f"Total expenses: {total}")

# Example usage:
tracker = ExpenseTracker()
tracker.add_expense(50, "Groceries")
tracker.add_expense(20, "Taxi")
tracker.view_expenses()
tracker.calculate_total()

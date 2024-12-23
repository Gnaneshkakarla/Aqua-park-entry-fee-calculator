# Aqua-park-entry-fee-calculator
from datetime import datetime

# Function to calculate entry fee
def calculate_fee(age, is_weekend):
    # Base prices (example)
    child_fee = 10  # $10 for children
    teenager_fee = 15  # $15 for teenagers
    adult_fee = 20  # $20 for adults
    senior_fee = 12  # $12 for senior citizens
    
    discount = 0  # No discount initially

    # Determine the entry fee based on age
    if age <= 12:
        entry_fee = child_fee
    elif 13 <= age <= 17:
        entry_fee = teenager_fee
    elif 18 <= age <= 64:
        entry_fee = adult_fee
    else:
        entry_fee = senior_fee

    # Apply discount if it's a weekend
    if is_weekend:
        discount = 0.1  # 10% discount on weekends
        print("Weekend discount applied!")

    # Calculate final fee after discount
    final_fee = entry_fee - (entry_fee * discount)
    return final_fee

# Main program to interact with the user
def main():
    # Get current day of the week
    current_day = datetime.now().weekday()  # 0 is Monday, 6 is Sunday

    # Determine if today is a weekend (Friday, Saturday, Sunday)
    is_weekend = current_day >= 4  # Friday (4) to Sunday (6)

    # Input age from user
    age = int(input("Enter your age: "))
    
    # Calculate and display the entry fee
    fee = calculate_fee(age, is_weekend)
    print(f"Your entry fee is: ${fee:.2f}")

# Run the program
if __name__ == "__main__":
    main()

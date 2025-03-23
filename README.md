def car_loan_calculator(loan_amount, interest_rate, loan_term, down_payment):
    # Adjust loan amount by subtracting down payment
    loan_amount -= down_payment
    
    # Convert annual interest rate to monthly and convert percentage to decimal
    monthly_interest_rate = (interest_rate / 100) / 12
    
    # Total number of payments (loan term in months)
    total_payments = loan_term * 12
    
    # Calculate monthly payment using the loan amortization formula
    if monthly_interest_rate > 0:
        monthly_payment = loan_amount * (monthly_interest_rate * (1 + monthly_interest_rate)**total_payments) / ((1 + monthly_interest_rate)**total_payments - 1)
    else:
        monthly_payment = loan_amount / total_payments  # If no interest
    
    # Calculate total loan repayment (monthly payment * total number of payments)
    total_repayment = monthly_payment * total_payments
    
    # Calculate total interest paid (total repayment - loan amount)
    total_interest = total_repayment - loan_amount
    
    return monthly_payment, total_repayment, total_interest

# Example usage:
loan_amount = float(input("Enter the loan amount: "))
interest_rate = float(input("Enter the_

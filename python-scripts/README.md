import re

def check_password(password):
    # Assessment criteria
    length_error = len(password) < 8
    digit_error = re.search(r"\d", password) is None
    uppercase_error = re.search(r"[A-Z]", password) is None
    special_char_error = re.search(r"[ !@#$%^&*(),.?\":{}|<>]", password) is None

    errors = [length_error, digit_error, uppercase_error, special_char_error]
    
    if any(errors):
        return "❌ Weak Password: Needs more complexity (length, numbers, caps, or symbols)."
    else:
        return "✅ Strong Password!"

# Test the checker
test_pass = input("Enter a password to test: ")
print(check_password(test_pass))


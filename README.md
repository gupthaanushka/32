import string

password = input("Enter your password: ")

length_cond = len(password) >= 8
digit_cond = any(ch.isdigit() for ch in password)
upper_cond = any(ch.isupper() for ch in password)
lower_cond = any(ch.islower() for ch in password)
special_cond = any(ch in string.punctuation for ch in password)

conditions_met = sum([digit_cond, upper_cond, lower_cond, special_cond])

if length_cond and conditions_met >= 4:
    print("Strong Password")
elif length_cond and conditions_met >= 3:
    print("Medium Password")
else:
    print("Weak Password")

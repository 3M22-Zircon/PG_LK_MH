# PG_LK_MH 



import random
import string

def generate_password(length, uppercase=True, lowercase=True, numbers=True, special_chars=True):
    characters = ''
    if uppercase:
        characters += string.ascii_uppercase
    if lowercase:
        characters += string.ascii_lowercase
    if numbers:
        characters += string.digits
    if special_chars:
        characters += string.punctuation

    if not characters:
        raise ValueError("At least one character type must be selected")

    return ''.join(random.choice(characters) for _ in range(length))

def main():
    print("Welcome to the Password Generator!")

    try:
        length = int(input("Enter the length of the password: "))
        uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
        lowercase = input("Include lowercase letters? (y/n): ").lower() == 'y'
        numbers = input("Include numbers? (y/n): ").lower() == 'y'
        special_chars = input("Include special characters? (y/n): ").lower() == 'y'

        password = generate_password(length, uppercase, lowercase, numbers, special_chars)
        print("Your generated password is:", password)
    except ValueError as e:
        print("Error:", e)

if __name__ == "__main__":
    main()

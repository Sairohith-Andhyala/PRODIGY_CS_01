def caesar_cipher(text, shift, encrypt=True):
    result = ""
    
    for char in text:
        if char.isalpha():  # Check if the character is a letter
            shift_amount = shift if encrypt else -shift  # Reverse shift for decryption
            new_char = chr(ord(char) + shift_amount)
            result += new_char
        else:
            result += char  # Keep non-letter characters the same
    
    return result

# Get user input
message = input("Enter your message: ")
shift = int(input("Enter shift value (e.g., 3): "))
choice = input("Type 'e' to encrypt or 'd' to decrypt: ").lower()

# Encrypt or decrypt based on user choice
if choice == 'e':
    encrypted_text = caesar_cipher(message, shift, encrypt=True)
    print("Encrypted Message:", encrypted_text)
elif choice == 'd':
    decrypted_text = caesar_cipher(message, shift, encrypt=False)
    print("Decrypted Message:", decrypted_text)
else:
    print("Invalid choice! Please enter 'e' or 'd'.")

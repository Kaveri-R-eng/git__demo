# git__demo
learning Git by apna collage and trying it to implement here
import random
import string

def generate_password(length=12, include_uppercase=True, include_lowercase=True, include_digits=True, include_special_chars=True):
  """Generates a random password of specified length with optional character sets.

  Args:
    length: The desired length of the password. Defaults to 12.
    include_uppercase: Whether to include uppercase letters. Defaults to True.
    include_lowercase: Whether to include lowercase letters. Defaults to True.
    include_digits: Whether to include digits. Defaults to True.
    include_special_chars: Whether to include special characters. Defaults to True.

  Returns:
    A randomly generated password string.
  """

  characters = ''
  if include_uppercase:
    characters += string.ascii_uppercase
  if include_lowercase:
    characters += string.ascii_lowercase
  if include_digits:
    characters += string.digits
  if include_special_chars:
    characters += string.punctuation

  if not characters:
    raise ValueError("At least one character set must be selected.")

  password = ''.join(random.choice(characters) for _ in range(length))
  return password
  

import random
import strin

def generate_password(length=12):
    """Generate a secure random password."""

    if length < 1 :
        raise ValueError("Password length must be at least 4")

    chars = string.ascii_letters + string.digits + "!@#$%^&*"

    password = [
        random.choice(string.ascii_lowercase),
        random.choice(string.ascii_uppercase),
        random.choice(string.digits),
        random.choice("!@#$%^&*")
    ]

    password.extend(random.choice(chars) for _ in range(length - 4))

    random.shuffle(password)

    return "".join(password)


def main( ):
    print("=== Password Generator ===")

    try:
        length = int(input("Enter password length: "))
        password = generate_password(length)

        print("\nGenerated Password:")
        print(password)

    except ValueError as error:
        print(f"Error: {error}")


if __name__ == "__main__":
    main()

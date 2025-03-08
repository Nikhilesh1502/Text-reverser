def reverse_characters(text):
    """Reverses the characters of the given text."""
    return text[::-1]

def reverse_words(text):
    """Reverses the order of words in the given text."""
    words = text.split()
    return ' '.join(reversed(words))

def main():
    while True:
        print("\nText Reverser")
        print("1. Reverse Character Order")
        print("2. Reverse Word Order")
        print("3. Exit")

        choice = input("Enter your choice (1/2/3): ").strip()

        if choice == "3":
            print("Exiting the program. Goodbye!")
            break

        if choice not in ["1", "2"]:
            print("Invalid choice! Please enter 1, 2, or 3.")
            continue

        text = input("Enter a sentence: ").strip()

        if not text:
            print("Error: Input cannot be empty!")
            continue

        if choice == "1":
            result = reverse_characters(text)
        else:
            result = reverse_words(text)

        print(f"Reversed Output: {result}")

        save_choice = input("Do you want to save the result to a file? (yes/no): ").strip().lower()
        if save_choice == "yes":
            file_name = input("Enter file name (with .txt extension): ").strip()
            try:
                with open(file_name, "w", encoding="utf-8") as file:
                    file.write(result)
                print(f"Reversed text saved successfully in '{file_name}'!")
            except Exception as e:
                print(f"Error saving file: {e}")

if __name__ == "__main__":
    main()

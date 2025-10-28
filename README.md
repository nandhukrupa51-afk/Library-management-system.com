# Library Management System in Python

books = []
issued_books = {}

def add_book():
    book = input("Enter book name: ")
    books.append(book)
    print(f"'{book}' has been added to the library.\n")

def display_books():
    if books:
        print("Available Books:")
        for book in books:
            print(f"- {book}")
    else:
        print("No books available.\n")

def issue_book():
    book = input("Enter book name to issue: ")
    user = input("Enter your name: ")
    if book in books:
        issued_books[user] = book
        books.remove(book)
        print(f"Book '{book}' issued to {user}.\n")
    else:
        print("Book not available!\n")

def return_book():
    user = input("Enter your name: ")
    if user in issued_books:
        book = issued_books.pop(user)
        books.append(book)
        print(f"Book '{book}' returned by {user}.\n")
    else:
        print("No book found for this user.\n")

def main():
    while True:
        print("\n===== Library Management System =====")
        print("1. Add Book")
        print("2. Display Books")
        print("3. Issue Book")
        print("4. Return Book")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == '1':
            add_book()
        elif choice == '2':
            display_books()
        elif choice == '3':
            issue_book()
        elif choice == '4':
            return_book()
        elif choice == '5':
            print("Exiting system... Goodbye!")
            break
        else:
            print("Invalid choice. Try again!\n")

if __name__ == "__main__":
    main()

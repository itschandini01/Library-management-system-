# Library-management-system-
simple Library management system 
# Simple Library Management System

# List to store books
books = []

# Function to add a book
def add_book():
    book_id = input("Enter Book ID: ")
    title = input("Enter Book Title: ")
    author = input("Enter Author Name: ")
    
    # Create a dictionary for the book
    book = {
        "ID": book_id,
        "Title": title,
        "Author": author
    }
    
    books.append(book)
    print(f"\nBook '{title}' added successfully!\n")

# Function to view all books
def view_books():
    if not books:
        print("\nNo books found.\n")
        return
    print("\n--- Library Books ---")
    for book in books:
        print(f"ID: {book['ID']}, Title: {book['Title']}, Author: {book['Author']}")
    print()

# Function to search for a book by ID or Title
def search_book():
    search_term = input("Enter Book ID or Title to search: ").lower()
    for book in books:
        if book["ID"].lower() == search_term or book["Title"].lower() == search_term:
            print(f"\nFound Book: ID: {book['ID']}, Title: {book['Title']}, Author: {book['Author']}\n")
            return
    print("\nBook not found!\n")

# Function to delete a book by ID
def delete_book():
    delete_id = input("Enter Book ID to delete: ")
    for book in books:
        if book["ID"] == delete_id:
            books.remove(book)
            print(f"\nBook ID {delete_id} deleted successfully!\n")
            return
    print("\nBook not found!\n")

# Main menu
def main():
    while True:
        print("=== Library Management System ===")
        print("1. Add Book")
        print("2. View Books")
        print("3. Search Book")
        print("4. Delete Book")
        print("5. Exit")
        
        choice = input("Enter your choice (1-5): ")
        
        if choice == '1':
            add_book()
        elif choice == '2':
            view_books()
        elif choice == '3':
            search_book()
        elif choice == '4':
            delete_book()
        elif choice == '5':
            print("Exiting Library Management System. Goodbye!")
            break
        else:
            print("\nInvalid choice! Please try again.\n")

# Run the program
main()


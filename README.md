Lab: Iterators and Comparators
# Library

Create a class __Book__, which should have three public properties:
- string Title
- int Year
- List\<string\> Authors

Authors can be __anonymous, one or many__. A Book should have only __one constructor__.

Create a class __Library__, which should store a collection of books and implement the __IEnumerable\<Book\>__ interface. 
- List\<Book\> books

A Library could be intilized __without books__ or __with any number of books__ and should have only __one constructor__.

Inside the Library class create a __nested class LibraryIterator__, which should implement the __IEnumerator\<Book\>__ interface. Try to implement the bodies of the inherited methods by yourself. You will need two more members:
- List\<Book\> books
- int currentIndex

Now you should be able to iterate through a Library in the Main method.

Implement the __IComparable\<Book\>__ interface in the existing class Book. The comparison between two books should happen in the following order:

- First sort them in ascending chronological order (by year)
- If two books are published in the same year, sort them alphabetically

Override the __ToString()__ method in your Book class, so it returns a string in the format:

- "{title} - {year}"

Change your Library class, so that it stores the books in the correct order.

Create a class __BookComparator__, which should implement the __IComparer\<Book\>__ interface and thus include the following method: 

- int Compare(Book, Book) 

BookComparator must compare two books by:

1.	Book title - alphabetical order
2.	Year of publishing a book - from the newest to the oldest

Modify your Library class once again to implement the new sorting.

## Examples
```c#
public static void Main()
 {
     Book bookOne = new Book("Animal Farm", 2003, "George Orwell");
     Book bookTwo = new Book("The Documents in the Case", 2002, "Dorothy Sayers", "Robert Eustace");
     Book bookThree = new Book("The Documents in the Case", 1930);  

     Library libraryOne = new Library();
     Library libraryTwo = new Library(bookOne, bookTwo, bookThree); 

     foreach (var book in libraryTwo)
     {
         Console.WriteLine(book);
     }
}
```
|Output|
|------|
Animal Farm - 2003<br>The Documents in the Case - 2002<br>The Documents in the Case - 1930

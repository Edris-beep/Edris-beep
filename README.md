public class Book {
    private String title;
    private String[] pages;
    private int currentPage;

    // Constructor
    public Book(String title, String[] pages) {
        this.title = title;
        this.pages = pages;
        this.currentPage = 0;
    }

    // Method to read the current page
    public String readCurrentPage() {
        if (currentPage < pages.length) {
            return "Page " + (currentPage + 1) + ": " + pages[currentPage];
        } else {
            return "No more pages.";
        }
    }

    // Method to turn the page (next or previous)
    public String turnPage(String direction) {
        if (direction.equals("next") && currentPage < pages.length - 1) {
            currentPage++;
        } else if (direction.equals("previous") && currentPage > 0) {
            currentPage--;
        } else {
            return "You are at the end or the beginning of the book.";
        }
        return readCurrentPage();
    }

    public static void main(String[] args) {
        // Create a three-page book
        String[] pages = {
            "Once upon a time in a land far away...",
            "The hero embarked on a journey to find the ancient treasure...",
            "Finally, after many adventures, the hero returned home victorious."
        };

        Book myBook = new Book("The Hero's Journey", pages);

        // Read and navigate through the book
        System.out.println(myBook.readCurrentPage()); // Read the first page
        System.out.println(myBook.turnPage("next"));  // Go to the second page
        System.out.println(myBook.turnPage("next"));  // Go to the third page
        System.out.println(myBook.turnPage("next"));  // Try going beyond the last page
        System.out.println(myBook.turnPage("previous")); // Go back to the second page
    }
}

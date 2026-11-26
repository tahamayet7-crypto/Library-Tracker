# Library Book Tracker

A basic ICT project built with HTML, CSS and JavaScript. It lets users manage a small collection of book records.

## Live Website

[Open Library Book Tracker](https://tahamayet7-crypto.github.io/Library-Tracker/)

## Features

- Add a book with a unique ID, title and author.
- Edit book details or cancel an edit.
- Delete a book after confirmation.
- Switch a book between Available and Borrowed.
- Search by title or author without matching letter case.
- Save records in browser localStorage.

## Group Members

| Member | Roll Number | Contribution |
|---|---|---|
| Ahmad Raza | 26K-0609 | HTML structure |
| M. Ali Kazmi | 26K-0548 | CSS styling |
| Taha Hamza | 26K-0566 | JavaScript functionality |

## How to Run

1. Download `index.html`.
2. Open it in a web browser.
3. Enter a Book ID, Title and Author, then click **Add Book**.

The combined HTML file includes the CSS and JavaScript. No installation is required. Saved records belong to the current browser profile and website; they are not shared automatically between devices. Browser storage must be available.

## Manual Test Cases

**Execution status: Not run.** This table describes test steps and expected results. It does not claim that the tests have passed. Record actual results when running the tests.

### Preparation

- Use a browser with localStorage enabled.
- Use disposable book records.
- Prepare these sample books when a test needs existing records:
  - **B001** - **The Hobbit** - **J.R.R. Tolkien**
  - **B002** - **1984** - **George Orwell**
- Restore the required sample records before each test. Clear the search field unless the test concerns searching.

| ID | Test | Steps | Expected result |
|---|---|---|---|
| TC01 | Add a valid book | Ensure B001 does not exist. Enter B001, The Hobbit and J.R.R. Tolkien. Click Add Book. | One new row appears with those details and Available status. The form clears. |
| TC02 | Required fields | Try adding a book with each field left empty in turn. Also try with all three fields empty. | Please fill in all the fields. appears. No record is added. |
| TC03 | Spaces without text | Enter only spaces in one field and valid text in the others. Click Add Book. | The spaces are treated as an empty value. The required-fields error appears and no record is added. |
| TC04 | Duplicate Book ID | Ensure B001 exists. Try adding another book using the exact ID B001. | This Book ID is already used. appears. The existing record remains unchanged and no duplicate is added. |
| TC05 | Edit book details | Click Edit on B001, change its title and author, then click Save Changes. | The existing row updates without adding another row. Its availability status is preserved. The form returns to add mode. |
| TC06 | Keep the same ID while editing | Click Edit on B001. Keep its ID unchanged, change its title, then save. | The edit is accepted. The record does not conflict with its own ID. |
| TC07 | Conflicting ID while editing | Ensure B001 and B002 exist. Edit B002, change its ID to B001 and click Save Changes. | The duplicate-ID error appears. The stored records remain unchanged. |
| TC08 | Cancel an edit | Edit B001, change a form value and click Cancel without saving. | The original record is unchanged. The form clears, Add Book returns and Cancel is hidden. |
| TC09 | Confirm deletion | Click Delete on a disposable record and accept the confirmation. | Only the selected record is removed from the table and saved collection. |
| TC10 | Cancel deletion | Click Delete on B001 and dismiss the confirmation using Cancel. | B001 remains unchanged. |
| TC11 | Change availability | Start with B001 Available. Click Change Status, then click it again. | Its status becomes Borrowed in red, then Available in green. |
| TC12 | Search by title | With both sample books present, type Hobbit into the search field. | The Hobbit appears and 1984 is hidden. |
| TC13 | Search by author | With both sample books present, type Orwell into the search field. | The George Orwell record appears and the Tolkien record is hidden. |
| TC14 | Search with different letter case | Search for hObBiT while The Hobbit exists. | The Hobbit still matches. |
| TC15 | No search matches and reset | Search for a value absent from all titles and authors, such as zzzunmatched999. Then clear the search field. | No books found. appears for the unmatched search. Clearing the search restores all records. |
| TC16 | Save changes after refresh | Add a disposable book, edit it and change its status. Refresh the same website in the same browser profile. | The record, edited details and selected status remain. |
| TC17 | Save deletion after refresh | Delete a disposable record and confirm. Refresh the same website. | The deleted record does not return. |
| TC18 | Empty collection | Delete all disposable records, confirming each deletion. Keep the search field empty. | The table has no book rows and No books found. appears. |
| TC19 | Display entered symbols as text | Add a book with the title `<Book & Notes>` and valid ID and author values. | The title appears as entered text. It is not interpreted as an HTML element. |
| TC20 | Readability on small screens | Resize the browser to 600 pixels wide or less. Inspect the page, table and action buttons. | Ordinary book details are readable in black on white. Status colours remain visible. Wide table content can be reached using horizontal scrolling. |

## Project Limitations

- No user accounts or online database.
- No borrower records, due dates or fines.
- Clearing browser site data can remove saved books.

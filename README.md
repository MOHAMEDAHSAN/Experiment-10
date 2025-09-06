### Name : S Mohamed Ahsan
### Reg No : 212223240089

# **Experiment-10**

## **Test Plan Document for Library Application**

### **Introduction**

The Library Management System (LMS) is an online application for assisting a librarian in managing a book library in a university.
The system would provide basic set of features to add/update clients, add/update books, search for books, and manage check-in / checkout processes.
Our test group tested the system based on the requirement specification.

This test report is the result for testing in the LMS. It mainly focuses on two problems:

1. What we will test
2. How we will test

---

### **GUI Test**

**Pass criteria**: librarians could use this GUI to interface with the backend library database without any difficulties
**Result**: Pass ✅

---

### **Database Test**

**Pass criteria**: Results of all basic and advanced operations are normal (refer to section 4)
**Result**: Pass ✅

---

### **Basic Function Test**

#### Add a student

**Pass criteria**:
Each customer/student should have following attributes: Student ID/SSN (unique), Name, Address and Phone number.
**Result**: Pass ✅

The retrieved customer information by viewing customer detail should contain the four attributes.
**Result**: Pass ✅

---

#### Update/delete student

**Pass criteria**:
The record would be selected using the student ID
**Result**: Pass ✅

Updates can be made on full items only: Name, Address, Phone number
**Result**: Pass ✅

The record can be deleted if there are no books issued by user.
**Result**: Partially Pass ⚠️ (When no books issued by user, he can be deleted. But when there are books issued by this user, he was also deleted — wrong behavior).

The updated values would be reflected if the same customer's ID/SSN is called for.
**Result**: Pass ✅

If customer were deleted, it would not appear in further search queries.
**Result**: Pass ✅

---

#### Add a book

**Pass criteria**: Each book shall have following attributes: Call Number, ISBN, Title, Author name.
**Result**: Pass ✅

The retrieved book information should contain the four attributes.
**Result**: Pass ✅

---

#### Update/delete book

**Pass criteria**:

* The book item can be retrieved using the call number
  **Result**: Did not Pass ❌ (cannot retrieve using call number)

* The data items which can be updated are: ISBN, Title, Author name
  **Result**: Pass ✅

* The book can be deleted only if no user has issued it
  **Result**: Partially Pass ⚠️ (when no user issued, pass; when issued, did not pass)

* The updated values would be reflected if the same call number is called for
  **Result**: Pass ✅

* If book were deleted, it would not appear in further search queries
  **Result**: Pass ✅

---

### **Search for Book**

**Pass criteria**:

* Librarian can query by ISBN, Author or Title → **Result: Pass ✅**
* Results show Call number, ISBN, Title, Author → **Result: Pass ✅**
* Show number of copies available for issue → **Result: Pass ✅**
* Allow multiple rows selection into user-list → **Result: Pass ✅**
* Detailed view shows check-in/check-out status and borrower info → **Result: Pass ✅**
* Max 20 results per page, with navigation → **Result: Pass ✅**
* Multiple searches allowed and stored → **Result: Pass ✅**
* Multiple copies of same ISBN show identical details → **Result: Pass ✅**
* Borrower’s list agrees with student account → **Result: Pass ✅**

---

### **Check-in Book**

**Pass criteria**:

* Check-in by call number → **Result: Pass ✅**
* Initiated from search results → **Result: Pass ✅**
* Return date auto = system date → **Result: Did Not Pass ❌**
* Late fees (10 cents/day) → **Result: Did Not Pass ❌**
* Book already checked in cannot be checked in again → **Result: Pass ✅**

---

### **Check-out Book**

**Pass criteria**:

* Check-out by call number → **Result: Pass ✅**
* Initiated from search results → **Result: Pass ✅**
* Student ID entered → **Result: Pass ✅**
* Issue date auto = current date → **Result: Did Not Pass ❌**
* Due date auto = current + 5 days → **Result: Did Not Pass ❌**
* Already checked-out book cannot be reissued → **Result: Pass ✅**
* Students with overdue books blocked → **Result: Did Not Pass ❌**
* Max 10 books per student → **Result: Pass ✅**

---

### **View Book Detail**

**Pass criteria**:

* Show Call number, ISBN, Title, Author, Issue status → **Result: Pass ✅**
* If checked out: show User ID, Name, Checkout Date, Due Date → **Result: Did Not Pass ❌**
* If checked in: no user summary → **Result: Pass ✅**
* Checked-out books show correct user details → **Result: Pass ✅**

---

### **View Student Detail**

**Pass criteria**:

* Librarians can select a user record → **Result: Pass ✅**

* Detail view should show:

  a. User name, ID, Address, Phone → **Result: Pass ✅**
  b. Issued books with Issue Date, Due Date, Call Number, Title → **Result: Did Not Pass ❌**
  c. Late fees & fines summary → **Result: Did Not Pass ❌**

* Display matches existing user profile → **Result: Pass ✅**

* Checked-out books marked correctly → **Result: Pass ✅**

* Book search query shows correct User ID → **Result: Pass ✅**

---


### **Alpha Testing**

**Pass criteria**: Internal testing by developers + QA team.
**Result**: Pass ✅ 

---

### **Beta Testing**

**Pass criteria**: Real users (librarians, students) test the system in live conditions.
**Result**: Partial Pass ⚠️ 

---

### **Acceptance Testing**

**Pass criteria**: Client validation against requirements.
**Result**: Partial Pass ⚠️ 

---

### **Performance Testing**

**Pass criteria**: System stable under concurrent users.
**Result**: Pass ✅ 

---

### **Result**

Thus, the Test cases for the library application were implemented and output was verified successfully.
Most modules worked as expected. Issues remain in:

* **Delete rules** (students/books with issues)
* **Date stamping** (issue/return/due dates not auto-updating)
* **Fine calculation & overdue restrictions**

Overall, the system is **functional but requires fixes before final deployment**. 


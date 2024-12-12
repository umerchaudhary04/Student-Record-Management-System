 Documentation: Student Record Management System in C++

 Overview:
 
This program is a Student Record Management System that allows the user to manage student data, including storing, displaying, updating, searching, and deleting student records. The records are stored in arrays, and the program provides a menu-driven interface to perform these actions interactively.

 Features:

1. Enter Student Data: Input student records including roll number, name, class, course, mobile number, and admission year.
2. Show Student Data: Display all the stored student records.
3. Search Student Data: Find a student by their roll number and display their details.
4. Update Student Data: Modify the existing student record by updating fields.
5. Delete Student Data: Delete all student records from the system.
6. Quit the Program: Exit the system.


 Code Structure:

 1. Global Variables and Arrays

```cpp
string roll_no[30], name[30], Class[30], course[30], mobile_no[30], admission_year[30];
int total = 0;
```

- Arrays:
  - `roll_no[30]`: Stores the roll numbers of students.
  - `name[30]`: Stores the names of students.
  - `Class[30]`: Stores the classes of students.
  - `course[30]`: Stores the courses of students.
  - `mobile_no[30]`: Stores the mobile numbers of students.
  - `admission_year[30]`: Stores the admission years of students.

- `total`: An integer that stores the total number of student records entered.



 2. Function: `enter()`

```cpp
void enter()
```

- Purpose: To input the details of one or more students.
- Details: 
  - First, the user is prompted to enter how many students they want to input.
  - If no records have been entered (`total == 0`), it collects data for the number of students specified.
  - If records are already present, new records are appended.
  - The program collects the following data for each student:
    - Roll Number
    - Name
    - Class
    - Course
    - Mobile Number
    - Admission Year



 3. Function: `show()`

```cpp
void show()
```

- Purpose: Displays all the student records entered.
- Details:
  - If no records exist (`total == 0`), it displays a message saying "No Data is Entered".
  - If records exist, it loops through the arrays and prints the details of each student.



 4. Function: `search()`

```cpp
void search()
```

- Purpose: Allows the user to search for a student by roll number.
- Details:
  - The user is asked to input the roll number of the student they wish to search.
  - If the student with the specified roll number exists, the student's details are displayed.
  - If no data is found or if `total == 0`, it will notify the user that no data is entered.



 5. Function: `update()`

```cpp
void update()
```

- Purpose: Allows the user to update an existing student's details.
- Details:
  - The user is prompted to input the roll number of the student they want to update.
  - If the student is found, their existing data is displayed, and the user is prompted to enter new data.
  - If no data exists (`total == 0`), it notifies the user that no data is available.



 6. Function: `Delete()`

```cpp
void Delete()
```

- Purpose: Deletes all the student records stored in the system.
- Details:
  - The user is asked if they are sure they want to delete all the data.
  - If the user presses `1`, the `total` is set to `0`, effectively deleting all records.
  - If `1` is not pressed, it prints a message asking the user to confirm.



 7. Function: `main()`

```cpp
int main()
```

- Purpose: The main function that contains the menu-driven interface to interact with the program.
- Details:
  - The program runs in an infinite loop (`while(true)`), continuously showing the menu options until the user chooses to exit.
  - The menu allows the user to:
    - Enter student data
    - Show all student records
    - Search a specific student by roll number
    - Update an existing student's record
    - Delete all records
    - Quit the program
  - The user's choice is handled using a `switch` statement.



 Menu Options:

1. Press 1: To input student data.
2. Press 2: To display all student records.
3. Press 3: To search for a student by roll number.
4. Press 4: To update a student's record.
5. Press 5: To delete all student records.
6. Press 6: To exit the program.



 Example Run:

1. Enter Data:  
   The user selects option 1 to enter student records. After inputting the required details, the data is stored.
   
2. Show Data:  
   The user selects option 2 to display all entered student records. The system prints out each student's information.

3. Search Data:  
   The user enters a roll number to search for a specific student. If the student exists, their details are displayed.

4. Update Data:  
   The user enters a roll number, and the system displays the current details of the student. The user is then prompted to update the student's data.

5. Delete Data:  
   The user selects option 5 to delete all records. If confirmed by pressing `1`, all student data is erased.

6. Quit the Program:  
   The user selects option 6 to exit the program.



 Example Output:

```
Press 1 to Enter data

Press 2 to Show data

Press 3 to Search data

Press 4 to Update data

Press 5 to Delete data

Press 6 to Quit

Enter the roll no of student
101
Enter Name: John Doe
Enter Class: 10
Enter Course: Science
Enter Mobile NO: 9876543210
Enter Admission Year: 2022

Press 1 to Enter data

Press 2 to Show data

Press 3 to Search data

Press 4 to Update data

Press 5 to Delete data

Press 6 to Quit

```


 Future Improvements:

1. Dynamic Memory Management: 
   - Currently, the system uses static arrays (`size = 30`). To handle a larger and dynamic number of students, you could replace arrays with `vector` to manage student data more efficiently.

2. Input Validation:
   - Add checks to ensure that the user inputs valid data, such as numeric values for phone numbers and admission year.

3. Advanced Search:
   - Improve search functionality to display a message when the student does not exist, or handle multiple students with the same roll number.

4. Persistent Storage:
   - Currently, data is lost when the program is closed. Implementing file I/O to store data in a file would allow persistence across sessions.

5. User Interface (UI):
   - You could enhance the UI by formatting the output to make it more readable or using a graphical interface (GUI) with libraries like `Qt` or `SFML`.

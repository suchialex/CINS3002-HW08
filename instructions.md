# Instructions

<details>
  <summary>
    💡 REPL/PyCharm Guide
  </summary>

  - To toggle commenting, highlight the line(s) and press Ctrl + /
  - To move a statement or block of statements one indent to the right, highlight the statement(s)  press Tab
  - To move a statement or block of statements one indent to the left, highlight the statement(s)  press Shift+Tab
  - Avoid using backspaces or spaces to remove or place indents
  - REPL Comments
    - To ask the instructor a code question, highlight the line(s) of code and press Alt + / and type in your question/issue/comment and click on collapse
    - To view comments placed by the instructor click on the comment icon at the end of any highlighted code
    - If your issue is resolved, click on Resolve to remove the comment
</details>


<details>
  <summary>
    Assignment Instructions
  </summary>

- In this assignment we manage employee data using classes and **storing these class objects in a dictionary**
- Each employee object has four data elements - Name, Department, Salary, Email
- All such employee objects are stored in a dictionary whose keys will be the employee ID
</details>


## Start Working

<details>
  <summary>
    ✅ Create a new PyCharm project
  </summary>

  - Create a new PyCharm project in a folder of your choice
  - Create a Python file - main.py
  - Inside the project create a new folder **hw08**
  - Create files classes.py, class_functions.py and validations.py
</details>

<details>
  <summary>
    ✅ Copy code from hw06
  </summary>

  - Copy main.py
  - Copy the code in validations.py from HW07
  - Copy the code from dict_functions 
  - Change the import statement in main.py to use class_functions module
  - **Instructor will not provide employee data file**, it will be created using your program's `Add Employee` option (_after we write code for that function_)
</details>

## In classes.py

<details>
  <summary>
    ✅ Define a class called employee
  </summary>

  - Use coding conventions for class name
</details>


<details>
  <summary>
    ✅ Define __init__() for the employee class
  </summary>

  - Because our employee has four data fields, accept for parameters in the \_\_init\_\_ definition
  - 🚩 Do not forget the default parameter
  - Bind the employee data parameters to the object using self assingment. Ensure these are private attributes.
</details>

<details>
  <summary>
    ✅ Define __str__() for the employee class
  </summary>

  - 🚩 Do not forget the default parameter in the definition
  - Inside the \_\_str\_\_() function body
    - Write a statement that returns a formatted string as follows
    - Make sure to use the private attributes you created in the \_\_init\_\_() in the appropriate placeholders

  Name: <employee_name>  
  Department: <employee_department>  
  Salary: <employee_salary>  
  Email: <employee_email>  

</details>

<details>
  <summary>
    ✅ Define accessor method get_name() in the employee class
  </summary>

  - 🚩 Do not forget the default parameter in the definition
  - Inside the get_name function body
    - Write a statement that returns the private attribute for the employee name
</details>

<details>
  <summary>
    ✅ Define accessor methods get_dept, get_salary, get_email in the employee class
  </summary>

  - Return the appropriate private attribute in each method
</details>


<details>
  <summary>
    ✅ Define mutator method set_name() in the employee class
  </summary>

  - Accept the new name (choose a name for this new name) as a parameter
  - 🚩 Do not forget the default parameter in the definition
  - Inside the set_name function body
    - Write a statement that assigns this new name to the existing private attribute for the employee name
</details>

<details>
  <summary>
    ✅ Define mutator methods set_dept and set_salary in the employee class
  </summary>

  - Return the appropriate private attribute in each method
  - In this project, we are not allowing the user to change the email address of an employee, hence we are not writing a mutator method for it
</details>

## In class_functions.py

<details>
  <summary>
    ✅ Import the employee class
  </summary>

  - Using the from keyword, import the employee class you created in classes module
</details>

<details>
  <summary>
    ✅ Modify file_to_dictionary()
  </summary>

  - In the body of file_to_dictionary, change the file location to hw08/employees.bin
</details>

<details>
  <summary>
    ✅ Modify employee_operations()
  </summary>

  - Comment out all the code except the file_to_dictionary call
  - Print the dictionary (it should print empty dictionary, if you have used exception handling in that function)
</details>


<details>
  <summary>
    ✅ Modify add_employee()
  </summary>

  - After the code to get all the employee data fields, create an object of the Employee class named `new_employee` by passing them in the same order as used in the initializer method  
  - To the employees dictionary add a new key/value pair
    - key is the calculated employee ID and
    - value is new employee object
    - ⏩ Refer to 9-4a
  - Print `Added Employee`
  - Return employees dictionary (optional if you decide to keep the dictionary name the same in all functions)
</details>

</details>

<details>
  <summary>
    ✅ Modify dictionary_to_file()
  </summary>

  - In the body of dictionary_to_file(), change the file location to hw08/employees.bin
</details>


<details>
  <summary>
    ✅ Call add_employee()
  </summary>
  
  - In employee_operations() function, uncomment whatever code you need to call
    - add_employee()
    - **and dictionary_to_file()**
  - Execute the program and add a new employee and Exit out of the program
  - If your code is correct, a new file called employees.bin will be created in hw08 folder. It should have some human un-readable data
  - This file will work with only your code (because the attribute names you may have chosen will not match with other students' choice)
</details>



<details>
  <summary>
    ✅ Modify lookup_employee()
  </summary>
  
  - Delete the print statement(s) in the if block and simply print the employee object at the key provided by the user
  - This print statement will call the str() method and print all the data correctly
  
</details>

<details>
  <summary>
    ✅ Call lookup_employee() after add_employee()
  </summary>

  - In employee_operations() function, uncomment whatever code you need to call lookup_employee
  - 📜 Test your code with the most recently added employee's ID
</details>


<details>
  <summary>
    ✅ Modify modify_name()
  </summary>

  - Inside the if block, after calculating the new name using calls to the validate_first_name and validate_last_name functions
  - Then we find the appropriate dictionary element using employee_id (converted to integer) as the key and store it in a variable, say `found_employee`
  - using this found_employee object, call the set_name method by passing the new name as argument
</details>
</details>


<details>
  <summary>
    ✅ Call modify_name()
  </summary>

  - In employee_operations() function, uncomment whatever code you need to call modify_name()
  - Test your code and make sure employee name is being modified correctly
</details>


<details>
  <summary>
    ✅ Same for modify_department, modify_salary
  </summary>

  - Do the same steps as above for modifying department and salary by calling the appropriate set/mutator methods defined in the class
</details>


<details>
  <summary>
    ✅ Modify display_employees()
  </summary>



<details>
  <summary>
    🔑 Code Logic:
  </summary>

  - Inside the for loop
    - Get each data element using the loop variable (employee object) and the appropriate get methods
    - For example, employee name would be  `<loop_variable>.get_name()`
    - Do the same for other data elements, department, salary, email etc
  - Display all these values in a tabular format
  - You may choose column widths and alignment to fit your data

</details>

</details>


<details>
  <summary>
    ✅ Call  display_employees()
  </summary>

  - Uncomment appropriate code in employee_operations function to call display_employees()
  - Test your code to make sure your employee(s) are being displayed correctly
</details>


<details>
  <summary>
    ✅ No action on delete_employee()
  </summary>

  - Nothing to change here, because we still have to delete an employee by deleting the dictionary element, which in this assignment is an object (it was a dictionary in the previous assignment)
</details>



<details>
  <summary>
    ✅ Call  delete_employee()
  </summary>

  - Uncomment code in employee_operations to call delete_employee()
  - 📜 Execute your code and ensure ALL employee operations are being performed correctly
</details>


## Copy code to replit

<details>
  <summary>
    ✅ Copy code to replit
  </summary>
  
  - Copy the contents of classes.py, validations.py and class_functions.py to replit under folder hw08
  - Upload your employees.pkl (it will NOT upload to hw08, you have to drag and drop it) - watch the solution video if you need help
  - Comment out the existing import statement and code in main function body
  - Copy the import statement and code from main.py in your PyCharm Project and paste it in the appropriate places in replit
  - Submit the URL on Canvas assignment
</details>

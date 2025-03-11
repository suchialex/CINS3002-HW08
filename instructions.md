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

- In this assignment we manage employee data using classes and objects in a complex dictionary
- Each employee has four data elements - Name, Department, Salary, Email
- That data will be stored in an object
- All such objects for each employee is stored in a dictionary whose keys will be the employee ID we calculate
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
  - Change the import statement in main.py to use class_functions module
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
</details>

## In dict_functions.py

<details>
  <summary>
    ✅ Import the employee class
  </summary>

  - Using the from keyword, import the employee class you created in classes module
</details>

<details>
  <summary>
    ✅ Define employee_operations
  </summary>

  - For now place the keyword pass
</details>

<details>
  <summary>
    ✅ Define function file_to_dictionary()
  </summary>
  
  - It accepts no parameters
  - It returns the employees dictionary
  - In the function body,
    - Check if there is any data in employees.pkl inside the hw07 folder
      - if no data, then return an empty dictionary
    - Using context manager, unpickle the contents of the file employees.pkl to a dictionary and store in a variable of your choice
    ⏩ Refer to 9-11
    - Print this dictionary and check contents (you may comment it out after)
    - Return this dictionary
</details>


<details>
  <summary>
    ✅ Modify employee_operations() function
  </summary>
  
  - Call the file_to_dictionary() after the pass statement
  - Print the returned dictionary
  - 📜 Execute your code to check if the dictionary is printed correctly, you may use suchi_print
</details>

## In validations.py

<details>
  <summary>
    ✅ Define get_next_empid_dict() function
  </summary>
  
  Parameters: Dictionary<br>
  Returns: Integer<br>
  Description: This functions finds the max employee ID in the dictionary and adds 1 to it and returns the next employee ID in a integer format<br>

<details>
  <summary>
    🔑 Code Logic:
  </summary>

  - If dictionary is empty, return 1234 (integer, not a string)
  - Get the dictionary keys of the employees dictionary and store in a variable ⏩ Refer to 9-9f
  - Get the max element from that ⏩ Refer to 7-15
  - Add 1 to the max key and return it
</details>

</details>

## In dict_functions.py

<details>
  <summary>
    ✅ Define add_employee() function
  </summary>

Parameters: Dictionary  
Returns: Dictionary  
Description: We add a new employee to the dictionary and return the modified dictionary.

<details>
  <summary>
    🔑 Code Logic:
  </summary> 

  - Employee ID is obtained from function call to get_next_employeeid() 
  - Name is obtained from function calls to validate_first_name() and validate_last_name()  
  - Email is obtained from a function call to generate_email()
  - Department is obtained from a function call to validate_dept()
  - Salary is obtained from a function call to validate_salary()
  - Using all these values create a dictionary named `new_employee` with the  key/value pairs  
  "name" -> Name  
  "dept" -> Department  
  "email" -> Email  
  "salary" -> Salary

  - Now, to the employees dictionary add a new key/value pair
    - key is the calculated employee ID and
    - value is new_employee dictionary
    - ⏩ Refer to 9-4a
  - Print `Added Employee`
  - Return employees dictionary
</details>

</details>


<details>
  <summary>
    ✅ Call add_employee()
  </summary>
  
  - In employee_operations() function, after the file_to_dictionary() call add_employee() by passing employees as the argument
</details>

<details>
  <summary>
    ✅ Define lookup_employee()
  </summary>

  Parameters: Dictionary, Integer - (employee dictionary, employee_id)  
  Returns: Boolean (True if employee is found, False if not found)  
  Description: We check if the employee ID is present in the employee dictionary and if found, print all the available data elements for that employee in a pretty format like this  
Name: Mia Rose  
Department: CINS  
Email: mia@company.com  
Salary: 45000

<details>
  <summary>
    🔑 Code Logic:
  </summary> 

  - Convert the user provided employee ID to integer (this might raise exception if user enteres non-numeric values, so use exception handling)
  - Using in operator check if the employee ID is in the dictionary   ⏩ Refer to 9-6c
  - If yes,
    - print the name, department, email and salary
    - return True
  - Else
    - print `Employee Not Found`
    - return False

🚩 Important: Before you print each data element, make sure that key exists for that employee. ⏩ Refer to 9-6c or use the get method with the second parameter
</details>
</details>

<details>
  <summary>
    ✅ Call lookup_employee() after add_employee()
  </summary>

  - Get user input for the employee ID that needs to be looked up
  - Call lookup_employee with the employees dictionary and the above employee ID as arguments
  - Test your code with the most recently added employee
</details>


<details>
  <summary>
    ✅ Define function modify_name()
  </summary>

  Parameters: Dictionary  
  Returns: Dictionary  
  Description: We use the lookup_employee function to see if the employee ID is present in our employee dictionary, if yes, we get the new name from the user and modify the dictionary appropriately
  
<details>
  <summary>
    🔑 Code Logic:
  </summary>
  
  - Ask user to provide the employee ID to modify name
  - Call the function lookup_employee using employees dictionary and the above employee ID as arguments and store returned value in a variable called found
  - if found is true
    - we ask the user to give us a valid name using a call to the validate_first_name and validate_last_name functions
    - Then we find the appropriate dictionary element and modify it  ⏩ Refer to 9-4a
    - 🚩 Do not forget to change the employee id to integer
    - Print `Name Modified Successfully`
  - Outside if block, return the employees
</details>
</details>


<details>
  <summary>
    ✅ Call modify_name() after lookup_employee()
  </summary>

  - Call modify_name using the employees dictionary as an argument
  - Print the employees dictionary (you may comment it out later)
  - Test your code and make sure employee name is being modified correctly
</details>


<details>
  <summary>
    ✅ Same for modify_department, modify_salary
  </summary>

  - Do the same steps as above for modifying department and salary
</details>


<details>
  <summary>
    ✅ Define display_employees()
  </summary>

  Parameters: Dictionary  
  Returns: None  
  Description: We use a for loop to go over the employee dictionary and print all data elements in a tabular format

<details>
  <summary>
    🔑 Code Logic:
  </summary>

  - Start a for loop to go over the employee dictionary's values
    - Get each data element using the loop variable
    - For example, employee name would be  `<loop_variable>.get("name", "-")`
    - Do the same for other data elements, department, salary, email etc
  - Display all these values in a tabular format
  - You may choose column widths and alignment to fit your data

</details>

</details>


<details>
  <summary>
    ✅ Call  display_employees()
  </summary>

  - Call display_employees() with the employees dictionary as argument
  - Test your code
</details>


<details>
  <summary>
    ✅ Define delete_employee()
  </summary>

  Parameters: Dictionary  
  Returns: Dictionary  
  Description: We use the lookup_employee function to see if the employee ID is present in our employee dictionary, if yes, we delete that employee from the dictionary
  
<details>
  <summary>
    🔑 Code Logic:
  </summary>
  
  - Ask user to provide the employee ID to delete
  - Call the function lookup_employee using employees dictionary and the above employee ID as arguments and store returned value in a variable called found
  - if found is true
    - Delete the appropriate dictionary element  ⏩ Refer to 9-6a
    - 🚩 Do not forget to change the employee id to integer
    - Print `Employee Deleted Successfully`
  - Outside if block, return the employees
</details>
</details>



<details>
  <summary>
    ✅ Call  delete_employee()
  </summary>

  - Call delete_employee() with the employees dictionary as argument
  - Print the employees dictionary to test (you may comment it out later)
</details>


<details>
  <summary>
    ✅ Define dictionary_to_file function
  </summary>

  Parameters: Dictionary  
  Return: None 

  - Pickle the employees dictionary to employees.pkl file in the employees folder  Refer to ⏩ 9-10

</details>

<details>
  <summary>
    ✅ Call  dictionary_to_file()
  </summary>

  - Call dictionary_to_file() passing the employees dictionary as argument
</details>

<details>
  <summary>
    ✅ Complete employee_operations() function
  </summary>

  - Call the file_to_dictionary() function
  - Inside a while loop that runs **until user presses 0**, print menu of options, get user's choice and inside the if-elif-else blocks calls the appropriate functions
  - Outside the while loop call dictionary_to_file() function
</details>


## Copy code to replit

<details>
  <summary>
    ✅ Copy code to replit
  </summary>
  
  - Copy the contents of validations.py and dict_functions.py to replit under folder hw07
  - Comment out the existing import statement and code in main function body
  - Copy and paste the import statement and code from main.py in your PyCharm Project
  - Submit the URL on Canvas assignment
</details>

## Data Validation

Data validation is the necessary step we follow after we have collected the data.

#### What Is Data Validation in Excel?
Data validation in Excel is a feature that allows you to control the type of data entered into a cell. It helps maintain accuracy and consistency by setting rules for what can be input. For example, you can restrict entries to whole numbers, decimals, dates, or a predefined list.


#### What Is the Purpose for Using Data Validation in Excel?
We can use Data Validation in our Excel worksheet because it-

- stops us from entering incorrect data in cells.
- Keeps our data uniformly formatted.
- Simplifies and speeds up our data input.
- Enhances our overall data reliability.
- Creates a positive user experience.
- Allows custom rules using formulas for our unique requirements.


1. Setting Up Data Validation
We start by preparing our spreadsheet and applying validation step by step.

1.1 Preparing the Dataset
We enter our data, such as a form with Name, Date of Birth, and Exam Centre columns, to apply validation rules.

1.2 Applying Basic Validation
Step 1: Click on the Data Tab in the Ribbon.

Step 2: Now select Data Validation.

<img width="1086" height="245" alt="image" src="https://github.com/user-attachments/assets/c217e206-b9c5-4218-b994-79fcf8d48295" />

After clicking on Data Validation, a menu appears.

<img width="184" height="168" alt="image" src="https://github.com/user-attachments/assets/dca9c7c3-fa28-4fea-946e-09860f896f83" />


Step 3: Select Data Validation and a dialogue box appear


<img width="394" height="318" alt="image" src="https://github.com/user-attachments/assets/7397a7d8-5667-4429-8093-24eb21561945" />

- There are 3 tabs in the dialogue box.

1. Settings: This will help we to select the data type and the type of data that we want to be filled in the desired row or column.
2. Input Message: This tab will help to let the user know about the constraints we've decided on for the row/column. It will alert the user to input the right set of values.
3. Error Alert: The error alert tab will help the user to know that they had entered invalid data.

- Note: The data validation feature is not 100 percent reliable. If we will try to copy the data from cells which has no defined validation rules and then try to paste those cells to cells having data validation then all the validation part get vanished. Basically, validation rules get changed from the corresponding cell based on the copied cell content.

2. Settings Tab
In the settings tab, we can find options to set validation criteria. The Setting Tab helps us to choose the validation rule as per our need from the in-built options. We also have the option to select custom rules with the customized formula for user inputs. There are all the options for Data Validation in the settings tab.


<img width="596" height="429" alt="image" src="https://github.com/user-attachments/assets/c6be49e2-aaa1-4e72-b8e4-42460dfb32a6" />

2.1 Input Message Tab (Optional)
The Input Message Text tab has a Text box to enter a message displayed as soon as the user selects the respective cell to enter the data.

We want to display a message that helps the user to understand what type of data is allowed to enter in the data in the given cell.

Follow the below steps:

Step 1: Open the Input Message Tab.

Step 2: Make sure there should be a tick mark on the "When a cell is selected, show input message".

Step 3: Enter the Title and Text of our message in the fields.

Step 4: As soon as the user selects the Validated cell, It will show this message.


<img width="779" height="440" alt="image" src="https://github.com/user-attachments/assets/8a4c4bce-9884-4794-b3a2-904ec53de100" />



2.2 Error alert Tab (Optional)
The error alert tab helps us to provide the option to control how the validation is enforced. We can apply different criteria and then use any desired error style according to the user input. We can also display a message to the user informing them about the type of error and what values must be entered in the given cells.

There are three types of error styles in Excel

1. Stop
2. Warning 
3. Information

If we want to configure a custom error alert message then follow the steps below:

- Step 1: Click on the Error Alert in the Data Validation

- Step 2: Make sure there is a tick mark in the box "Show error alert after invalid data in Entered".

- Step 3: We can Select the desired error style in the Style box.

- Step 4: Enter the title and text of the error message and click "ok".


<img width="595" height="423" alt="image" src="https://github.com/user-attachments/assets/ca0aef43-aba4-4551-8ca2-efc4082620a3" />


3. Excel Data Validation List
Data Validation also provides a feature of adding a drop-down list to a cell or group of cells.

Follow the below steps to add a drop-down list:

- Step 1: Select a cell in which we want to add the drop-down list.

- Step 2: On the setting tab,  Enter List in the Allow box.

- Step 3: Type the Items of our  Excel Validation list in the Source Box, Separated by commas For example To limit the user input into two choices type Yes, NO.

- Step 4: Now select the In-cell dropdown box in order for the drop-down arrow to appear next to the cell. 

- Step 5: Press "OK"


<img width="589" height="427" alt="image" src="https://github.com/user-attachments/assets/44215528-10cb-4afb-94c8-c836cbe7c6a7" />


### Example of Data Validation
Let's take the example of filling out a form. The form requires our name which has a limitation of 3-7 characters, it requires our date of birth, and has a list of cities for the exam center. Not considering all the other requirements as of now.

The form looks like this.

<img width="320" height="133" alt="image" src="https://github.com/user-attachments/assets/3411d067-003d-4a85-b369-5a67ed026044" />


To apply data validation with a word limit of 3-7 characters for the Name cell.

- Step 1: Select the empty cell in front of the Name.

- Step 2: From the DATA tab in the ribbon, select Data Validation.

- Step 3: A Dialogue box will appear.

- Step 4: In the dialogue box from the setting tab, in the dropdown, select Text Length (as shown in the image below).


<img width="402" height="325" alt="image" src="https://github.com/user-attachments/assets/50e6aefa-032c-4c6a-a7d2-1467f76697f4" />



- Step 5: We want our user to enter the name between 3-7 characters, So in the Minimum column we'll write 3 and in the Maximum column we'll write 7 and then click OK.


<img width="406" height="317" alt="image" src="https://github.com/user-attachments/assets/77389e98-9bef-4361-89fb-84bc0e64eba5" />




The Name row will now accept only text between 3-7 characters.

### 3.1 To use Data Validation as Date of Birth

- Step 6: Select the cell in front of Data of Birth in Excel.

- Step 7: Repeat steps 2 and 3.

- Step 8: In this step, instead of selecting text length, we need to select Date (as shown in the image below).

<img width="393" height="317" alt="image" src="https://github.com/user-attachments/assets/2da203cb-c49e-4479-8171-74368c23375a" />


We want to user must be born between 1st January 2000 to 1st January 2021.  Enter the Start date as 1st January 2000 and the End date as 1st January 2021. 


<img width="396" height="317" alt="image" src="https://github.com/user-attachments/assets/e7ce1200-8711-4a7a-86ed-d79e52b495f4" />


### Step 9: Click OK.

Now, the Date of Birth row will accept dates between 1st January 2000 to 1st January 2021.

### 3.2 Excel Data Validation List (Dropdown)
- Step 10: Select the empty cell in front of the Exam Centre.

- Step 11: Repeat steps 2 and 3.

- Step 12: Select List (as shown in the image below).


<img width="396" height="315" alt="image" src="https://github.com/user-attachments/assets/23e84b87-ded4-43c7-aff9-a382f47f4f00" />

We want to add "Kanpur", "Agra", "Aligarh", "Lucknow", "Varanasi" to the list.

- Step 13: Add the names in the source column separated by a comma(,).

<img width="393" height="314" alt="image" src="https://github.com/user-attachments/assets/18505df0-5e5a-4796-8d9c-8e05491d864f" />


- Step 14: Click OK.

- we've successfully created a form with 3 requirements using Data Validation.














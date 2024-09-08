# User Interface Specification: User Management Screen

![Screenshot 2024-09-08 at 11 41 25](https://github.com/user-attachments/assets/d72e62aa-4954-4374-bd3a-d9d8d604cdb2)

## 1. Overview
The **User Management Screen** provides an interface for managing users in the system. Users can be created, edited, or filtered based on certain criteria, such as username, email, and enabled/disabled status.

---

## 2. UI Components

### 1. **New User Button**
- Located at the top left of the screen.
- Allows the user to open the "New User" form to add a new user to the system.
- Button text: `+ New User`
- **Behavior**: When clicked, the form on the right side becomes active to input the new user details.

### 2. **Hide Disabled User Checkbox**
- Located beside the New User button.
- Checkbox label: `Hide Disabled User`
- Default state: **Unchecked**
- **Behavior**:
    - When checked, the list only shows enabled users.
    - When unchecked, both enabled and disabled users are shown.

### 3. **User List Table**
- Displays the list of existing users.
- Columns include:
    - **ID**: Unique identifier for the user.
    - **User Name**: Displayed name of the user.
    - **Email**: Email address of the user.
    - **Enabled**: Boolean value indicating if the user is enabled or disabled.
- Each column supports sorting (indicated by the up/down arrows).
- **Behavior**:
    - When a user is selected from the list, their details will be populated in the "New User" form for editing.

### 4. **New User Form**
- Located on the right side of the screen, used for creating or editing user information.
- Fields include:
    - **Username**: Text input for the user's username. (Required)
    - **Display Name**: Text input for the display name.
    - **Phone**: Text input for the phone number.
    - **Email**: Text input for the user's email address. (Required)
    - **User Roles**: Dropdown to select roles (Guest, Admin, SuperAdmin). Multiple selections allowed.
    - **Enabled**: Checkbox to set whether the user is enabled or disabled.
- **Save Button**:
    - Located in the top right of the form.
    - Label: `Save User`
    - **Behavior**: Saves the new or edited user details.

---

## 3. Behavior

### 1. **Initial Page Load**
- The user list table will display all users, both enabled and disabled, sorted by `ID` in ascending order.
- The "New User" form will be blank.

### 2. **New User Creation**
- When the `+ New User` button is clicked, the "New User" form becomes active, allowing the user to input data.
- The `Save User` button becomes clickable when the required fields (`Username`, `Email`) are filled.
- Upon clicking `Save User`, the new user is added to the table, and the form resets.

### 3. **Editing Existing Users**
- When a user is selected from the table, their details are loaded into the form.
- The user details can be modified, and the `Save User` button will save the changes.

### 4. **Hiding Disabled Users**
- If the `Hide Disabled User` checkbox is checked, the table will only display enabled users.
- If unchecked, all users are displayed.

### 5. **Sorting and Filtering**
- Each column in the user table allows sorting by clicking the up/down arrows.
- **Sorting behavior**: Ascending/Descending order for columns (ID, User Name, Email, Enabled).

---

## 4. Validation and Error Handling

### 1. **Required Fields**:
- `Username` and `Email` are mandatory fields. If these fields are empty and the user attempts to save, an error message should be displayed.

### 2. **Field Validation**:
- The `Email` field should validate if the input is in a valid email format.
- The `Phone` field should only accept numbers.

### 3. **Error Messages**:
- If any required fields are missing or invalid, an error message should be displayed next to the respective fields or as a toast notification.

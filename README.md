# Robot-Command-Display-Interface
This project extends the functionality of the Robot Control Web Interface by introducing a page that displays the last five commands sent to the robot. The commands are visually represented in a clean and modern interface, with the most recent command highlighted for easy identification.

## **Features**

- **Command History Display**: View the last five commands sent to the robot, with the most recent command prominently highlighted.
- **Visual Feedback**: The last command is highlighted with a unique color and an arrow for emphasis.
- **Responsive Design**: The interface is designed to be responsive, ensuring it looks good on all devices.

## **Project Structure**

```bash
robot_control/
├── show_data.html          # Web interface for displaying the last five commands
├── get_last_five_values.php # Backend script to retrieve the last five commands
└── README.md               # This readme file
```

## **Setup Instructions**

### **1. Prerequisites**

- **XAMPP** or any other local server environment with Apache and MySQL support.
- The database and table set up as described in the first task.

### **2. Database Setup**

The database should already be set up if you've completed the first task. If not, follow these steps:

1. Open **phpMyAdmin** (or your preferred database management tool).
2. Create a new database named `robot_control`.
3. Create a table named `robot_commands` using the following SQL query:

```sql
CREATE TABLE `robot_commands` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `command` varchar(255) NOT NULL,
  `timestamp` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
);
```

**Example of the Database Table Structure:**

![Database Table Structure](https://github.com/reham-ali102/Robot-Command-Display-Interface/blob/main/Database.PNG)

### **3. Project Setup**

1. Download or clone the repository into your local server’s root directory (e.g., `C:/xampp/htdocs/robot_control/`).

2. Place the project files (`show_data.html`, `get_last_five_values.php`) in the `robot_control` directory.

3. Ensure that your Apache server is running.

### **4. Running the Project**

1. Open your web browser.
2. Navigate to the display interface by entering the following URL:
   ```
   http://localhost/robot_control/show_data.html
   ```
3. The page will load and display the last five commands sent to the robot. The most recent command will be highlighted with a unique color and an arrow.

**Example of the Command Display Interface:**

![Command Display Interface](images/command-display.png)

### **5. File Descriptions**

- **show_data.html**: The user interface that displays the last five commands sent to the robot. The interface is styled to highlight the most recent command with an arrow and distinct color.
- **get_last_five_values.php**: This PHP script retrieves the last five commands from the `robot_commands` table in the MySQL database and returns them as a JSON response to be displayed on the page.

. **Images:**

   ![Database Table Structure](images/database.png)
   ![Command Display Interface]([images/command-display.png](https://github.com/reham-ali102/Robot-Command-Display-Interface/blob/main/command%20page.PNG))
 
### **6. Customization**

- **Change the Number of Commands Displayed**: By default, the page shows the last five commands. To show more or fewer commands, you can modify the `LIMIT` clause in the `get_last_five_values.php` file and adjust the HTML accordingly.
  
- **Modify Highlighting Styles**: You can easily change the highlighting style by editing the CSS in `show_data.html`. Adjust the colors, sizes, or even add new animations to the most recent command.

### **7. Troubleshooting**

- **404 Not Found**: Ensure that all files are correctly placed in the `htdocs` directory and that your URL is correctly pointing to `http://localhost/robot_control/show_data.html`.
- **No Commands Displayed**: If the interface displays "No Data," ensure that the `robot_commands` table contains data. You can test this by manually inserting commands into the table via phpMyAdmin or by using the first task's interface.
- **Database Connection Errors**: Verify your MySQL connection details in `get_last_five_values.php`. Ensure the MySQL service is running and the database credentials are correct.

### **8. Next Steps**

- **Enhancements**: Implement additional visualizations, such as graphs or charts showing command history trends. Add filtering options to view specific types of commands.
- **Integration**: Combine this display interface with the control interface from the first task to create a comprehensive robot command center.

### **9. License**

This project is licensed under the MIT License. Feel free to use and modify it for your own projects.

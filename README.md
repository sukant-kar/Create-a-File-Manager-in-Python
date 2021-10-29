# Create-a-File-Manager-in-Python
Step 1: Importing required modules
We will import the following modules:

Tkinter: It provides wide APIs for GUI functionalities.
Shutil: This module offers a number of high-level operations on files and collections of files.
Os: utility module for OS interaction in programs.
easygui:  It allows us to select any file from the system
Filedialog: This library is used for folder selection
Imageio: Used to read the file which is chosen by file box using a path
Any File Manager has several functions. Today, we will provide every possible feature to our file manager. Thus, every button will have certain functions to exhibit.

So, let’s begin with defining the functions.

Step 2: Defining functionalities
In this step, we will define all the functions which will be linked afterward to different buttons

Step 2.1: Opening a file box
The above code opens the file box, i.e the pop-up box to choose the file from the device, which opens every time you run the code. fileopenbox() is the method in easyGUI module which returns the path of the chosen file as a string.

We will call this function every time we want to select any file.

Step 2.2: Opening a file
Opening a file when Open a file button is clicked
The above code calls open_window() function and stores the returned path of file chosen in variable “string”. If a file is chosen os.startfile(string) function opens the file. Otherwise it opens a popup message box using mb.showinfo(‘confirmation’, “File not found!”).

Step 2.3: Copying a file
Copying a file when copy a file button is clicked
he above code calls open_window() function and stores the returned path of file chosen in variable “source1”. Variable “destination 1” stores the address of the folder returned by askdirectory() function in filedialog module.
shutil.copy(source1, destination1) copies a file present at source1 to destination1 address. As a result, it opens a popup message box using mb.showinfo(‘confirmation’, “File Copied !”).

Step 2.4: Deleting a file
Deleting a file when Delete a file button is clicked
The above code calls open_window() function and stores the returned path of file chosen in variable “string”. If a file is chosen os.remove(string) function deletes the file. Otherwise, it opens a popup message box using mb.showinfo(‘confirmation’, “File not found!”).

Step 2.5: Renaming a file
Renaming a file when Rename a file button is clicked
The above code calls open_window() function and stores the returned path of file chosen in variable “chosenFile”. Then, variable path1 is used to store the path of directory of the file chosen. os.path.splitext() splits the path into root and extensions. As we rename the file, we keep the same extension but need to manipulate only the name of the file mentioned in the root part.

Now, program asks the new name of the file. Once entered, the new name of file is stored in “newName” variable. Finally, we join newname to root and join it to extension, forming the path of the file with a new name.

os.rename(chosenFile,newName) function renames the chosen file. And, there appears a popup message box using mb.showinfo(‘confirmation’, “File Renamed !”) for confirmation.

Step 2.6: Moving a file
Moving a file when Move a file button is clicked
The above code calls open_window() function and stores the returned path of file chosen in variable “source”. And, the variable “destination” stores the address of destination folder address using filedialog.askdirectory().

If source and destination are the same, it opens a pop up box saying “Source and destination is same”. Else, the file is moved and opens a popup message box using mb.showinfo(‘confirmation’, “File Moved !”).

Step 2.7: Making a folder
Making a file when Make a folder button is clicked
Above code uses askdirectory function to open pop up box to select the folder and stores the returned path of the folder chosen in the variable “newFolderPath”.

Now, the program asks for the name of the new folder and stores it in the “new/folder” variable.

os.path.join() method in Python is used to join one or more path components intelligently. This method concatenates various newFolderPath and nerFolder with exactly one directory separator (‘/’) following non-empty parts except the last path component. Once the appended path is stored in “path” variable, mkdir() method creates a folder at the chosen folder. Finally, a popup message box is displayed using mb.showinfo(‘confirmation’, “Folder Created !”).

Step 2.8: Deleting a folder
Deleting when Delete a folder button is clicked
The above code uses askdirectory function to open pop up box to select the folder and stores the returned path of folder chosen in the variable “delFolder”.

Now, rmdir() method deletes the folder selected. Finally, a popup message box is displayed using mb.showinfo(‘confirmation’, “Folder Created !”).

Step 2.9: Listing files in a folder
Listing files in a folder when List all files in a directory button is clicked.
The above code uses askdirectory function to open pop up box to select the folder and stores the returned path of the folder chosen in the variable “folderList”.

Now, lstdir() method returns the list of all the files present in the folder selected. The list is sorted, and displayed using a while loop.

Step 3: Building File Manager UI using Tkinter
The above code is used to create a tkinter UI.

root=TK() is used to make a window. We use canvas() to create a canvas, and an image is applied in the background of our window using ImageTk.

Tkinter has two types of layout managers, grid and pack. For layout simplicity, we use a grid layout manager. Simply, using grid, we place every button in a single column.

Label() is used to place text label in the root window, with defined font, font size, and color. Row and column are also specified at the end.

Button() function placed in root window with text specified as text=”..” . The next parameter, “command” specifies the function which gets executed whenever a button is clicked. Please note, the function is specified without brackets in the statement. Similar to label, in every grid widget, we can specify row and column. To place the buttons one below the other, we specify the same column number, but change the row according to our need.

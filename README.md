<h1>Parsing Files Content</h1>


<h2>Project description and scenario</h2>

I am a cybersecurity professional working at a private health care company. I was asked to update the list of employees that have access to sensitive information. The IP addresses of these employees are included in a file called `"allow_list.txt"`. There's also a separate list that identifies which employees must be remove from `"allow_list.txt"`. Below is an explanation of how I created an algorithm using Python to automate the update of the restricted list.
<br />

<h2>Project walk-through:</h2>

<h3><p align="center">Open the file that contains the allow list:</h3>

Firstly, I assigned `"allow_list.txt"` as a string belonging to variable called `import_file`:
<br/>

<img width="50%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/8e4fbf8d-3dfc-48c7-956a-eafb9a0e7ab9"><br/>

As the second step, I used a `with` statement to open the file:
<br/>

<img width="50%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/9379ebed-1620-4ff8-a1e4-f65cdda4432e"><br/>

The `with` statement allowed me to use the `.open()` function to access the content of the file in read mode. This is possible by specifying the name of the file to open and the action I want to perform on the file, through the two parameters of the `.open()` function included within the `()`. In this case, with the first parameter I call `import_file`, whilst with the second parameter I specify that I want to read the file by including the string `“r”`. The code also uses the as keyword to assign a variable named `file` which stores the output of the `.open()` function. `with` automatically closes the file after the `with` statement has run.<br/>

<h3><p align="center">Read the file contents:</h3>

To be able to read its content, the file has to be converted into a string. For this purpose, I used the `.read()` method:
<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/1353ca32-c5eb-4cb9-8b3a-c57efefbbb95">
<br/>

I can now call a `.read()` method directly within the body of with. `.read()` directly converts files into strings that are readable in Python. For that reason, I used the following syntax:
<br/>

```ip_addresses = file.read()```
<br/>

This allowed me to convert the content of file into a string. At the same time, I assigned it to a new variable called `ip_addresses`, to simplify usability in the future.<br/>

<h3><p align="center">Convert the string into a list:</h3>

To remove individual IP addresses from the `"allow_list.txt"`, I needed its content to be in list format. Therefore, I next used the `.split()` method to convert the `ip_addresses` string into a list:<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/92349b97-e0d0-45c7-ab0a-7b9e5692a6e3"><br/>

The `.split()` function is called by appending it to a string variable. The purpose of splitting `ip_addresses` into a list is to make it easier to remove IP addresses from the allow list. By default, the `.split()` function splits the text by whitespace into list elements. In this algorithm, the `.split()` function takes the data stored in the variable `ip_addresses`, a string of elements each separated by a whitespace, and converts it into a list. To store this list, I reassigned it back to the variable `ip_addresses`.<br/>



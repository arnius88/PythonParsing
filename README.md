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


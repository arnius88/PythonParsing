<h1>Parsing Files Content</h1>


<h2>Project description and scenario</h2>

I am a cybersecurity professional working at a private health care company. I was asked to update the list of employees that have access to sensitive information. The IP addresses of these employees are included in a file called `"allow_list.txt"`. There's also a separate list that identifies which employees must be remove from `"allow_list.txt"`. Below is an explanation of how I created an algorithm using Python to automate the update of the restricted list.
<br />

<h2>Project walk-through:</h2>

<h3><p align="center">Open the file that contains the allow list:</h3>

Firstly, I assigned `"allow_list.txt"` as a string belonging to a variable called `import_file`:
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

I can now call a `.read()` method directly within the body of `with`. `.read()` directly converts files into strings that are readable in Python. For that reason, I used the following syntax:
<br/>

```ip_addresses = file.read()```
<br/>

This allowed me to convert the content of `file` into a string. At the same time, I assigned it to a new variable called `ip_addresses`, to simplify usability in the future.<br/>

<h3><p align="center">Convert the string into a list:</h3>

To remove individual IP addresses from the `"allow_list.txt"`, I needed its content to be in list format. Therefore, I next used the `.split()` method to convert the `ip_addresses` string into a list:<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/92349b97-e0d0-45c7-ab0a-7b9e5692a6e3"><br/>

The `.split()` function is called by appending it to a string variable. The purpose of splitting `ip_addresses` into a list is to make it easier to remove IP addresses from the allow list. By default, the `.split()` function splits the text by whitespace into list elements. In this algorithm, the `.split()` function takes the data stored in the variable `ip_addresses`, a string of elements each separated by a whitespace, and converts it into a list. To store this list, I reassigned it back to the variable `ip_addresses`.<br/>

<h3><p align="center">Iterate through the remove list:</h3>

At this point, I needed to iterate through the list of IP addresses within `ip_addresses`. To do this, I used a `for` loop, which, in Python, repeats code for a specific sequence.<br/>

<img width="50%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/c12c4c9a-c8cf-4cce-bcf0-08389d8a29e1"><br/>

The overall purpose of the `for` loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The `for` keyword starts the `for` loop. It is followed by the loop variable `element` and the keyword `in`. The keyword `in` indicates to iterate through the sequence `ip_addresses` and assign each value to the loop variable `element`.<br/>

<h3><p align="center">Remove IP addresses that are on the remove list:</h3>

Moving on, I needed to build a conditional statement that would allow me to remove the elements of `ip_addresses` that are also contained in `remove_list`. I placed the statement inside the body of the `for` loop:<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/ad2e5e93-b48b-4627-b5b7-6e515db5c766">

The conditional statement is opened by the `if` keyword. In essence, the statement is saying that if any element of the `ip_addresses` list is also found in `remove_list`, then the specific element should be removed from `ip_addresses`. I achieved this by appending the `.remove()` method using the following syntax:<br/>

```ip_addresses.remove(element)```
<br/>

`element` was assigned as the argument of the `.remove()` method. This way the loop iteration was able to remove each IP addresses marked in the `remove_list` from the `ip_addresses` list.
<br/>

<h3><p align="center">Update the file with the revised list of IP addresses:</h3>

Next step was about updating the original allow list file with the revised list of authorized IP addresses. The first thing I needed to do was to convert the list back into a string using the `.join()` method.<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/28b30ee8-6775-4672-8091-c97f909004f2"><br/>

The `.join()` method takes in an iterable as its argument and concatenates every element of it into a string. In this case, the argument of the `.join()` method is `ip_addresses`. The `.join()` method is appended to a string consisting of the character that will be used to separate every element in the iterable once this is converted into a string. In my case, I use the string `"\n"`, which instructs Python to place each element into a new line. I reassigned the syntax to the same variable `ip_addresses`, so I was able to use it later in conjunction with the `.write()` method.<br/>

<img width="80%" alt="image" src="https://github.com/arnius88/PythonParsing/assets/152484037/0a3e6127-5bb3-45c7-a082-13e4911ca267"><br/>

In the following step, the write statement allowed me to open the original `import_file` using `.open()`, once again. In this case, the second argument of the `.open()` method was `”w”` which clarifies that I want to overwrite the content already present in `import_file`.<br/>

To make sure that the data in `"allow_list.txt"` is updated and that only authorized users can access restricted information, I needed to write over the existing content of the allow list using the `.write()` method. I did this by appending `.write()` to the `file` object and passing the `ip_addresses` variable as its argument.<br/>

<h3><p align="center">Project Summary:</h3>

I created an algorithm that removes IP addresses identified in a `remove_list` variable from the `"allow_list.txt"` file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable `ip_addresses`. I then iterated through the IP addresses in `ip_addresses`. With each iteration, I evaluated if the element was part of the `remove_list` list. If it was, I applied the `.remove()` method to it to remove the element from `ip_addresses`. After this, I used the `.join()` method to convert the `ip_addresses` back into a string so that I could write over the contents of the `"allow_list.txt"` file with the revised list of IP addresses.<br/>

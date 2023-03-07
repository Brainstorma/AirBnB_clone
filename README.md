# AirBnB Clone - The Console

This project is a simple version of Airbnb for educational purposes. It consists of a command interpreter that allows you to manipulate data without a graphical interface, such as creating, updating and deleting objects.

## Command Interpreter

The command interpreter is a program that allows you to execute commands in a shell-like environment. It supports basic commands such as `help`, `quit`, `EOF`, etc. as well as some custom commands that are specific to this project.

### How to start it

To start the command interpreter, you need to clone this repository and run the file `console.py` with Python 3. You can run it in two modes:

- Interactive mode: run `./console.py` and type commands one by one, followed by enter. To exit, type `quit` or press Ctrl-D.
- Non-interactive mode: run `echo "command" | ./console.py` where "command" is the command you want to execute.

### How to use it

The command interpreter follows this syntax: `<command> [<class name>] [<id>] [<attribute name>] ["<attribute value>"]`. You can use spaces or tabs to separate the elements of the command. The command interpreter supports some built-in commands that are listed below:

- `help`: displays help information for a command
- `quit`: exits the program
- `EOF`: exits the program
- `create`: creates a new instance of a class and prints its id
- `show`: prints the string representation of an instance based on its class name and id
- `destroy`: deletes an instance based on its class name and id
- `all`: prints all string representation of all instances based or not on the class name
- `update`: updates an instance based on its class name and id by adding or updating attribute
- `<class name>.all()`: retrieves all instances of a class
- `<class name>.count()`: retrieves the number of instances of a class
- `<class name>.show(<id>)`: retrieves an instance based on its ID
- `<class name>.destroy(<id>)`: destroys an instance based on his ID
- `<class name>.update(<id>, <attribute name>, <attribute value>)`: updates an instance based on his ID

You can also use any executable file or script in your PATH as a command.

### Examples

Here are some examples of how to use the command interpreter:

```bash
$ ./console.py 
(hbnb) create BaseModel 
49faff9a-6318-451f-87b6-910505c55907
(hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907 
[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'id': '49faff9a-
6318-
451f-
87b6-
910505c55907', 'created_at': datetime.datetime(2017,
9,
28,
21,
5,
54,
119427), 'updated_at': datetime.datetime(2017,
9,
28,
21,
5,
54,
119572)}
(hbnb) destroy BaseModel 49faff9a -6318 -451f -87b6 -910505c55907 
(hbnb) show BaseModel 49faff9a -6318 -451f -87b6 -910505c55907 
** no instance found **
(hbnb) create User 
38dd69d5 -
3da4 -
4db4 -
b063 -
037ec2e01dc7 
(hbnb) update User 38dd69d5 -3da4 -4db4 -b063 -037ec2e01dc7 first_name "Betty"
(hbnb) show User 38dd69d5 -
3da4 -
4db4 -
b063 -
037ec2e01dc7 
[User] (38dd69d5-
3da4-
4db4-
b063-
037ec2e01dc7) {'id': '38dd69d5-
3da4-
4db4-
b063-
037ec2e01dc7', 'created_at': datetime.datetime(2017,
9,
28,
21,
11,
23),
'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 23), 'first_name':
'Betty'}
(hbnb) User.all()
[[User] (38dd69d5-3da4-4db4-b063-037ec2e01dc7) {'id': '38dd69d5-3da4-4db4-b063-037ec2e01dc7', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 23), 'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 23), 'first_name': 'Betty'}]
(hbnb) User.count()
1
(hbnb) quit
$

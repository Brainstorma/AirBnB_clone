# 0x00. AirBnB clone - The console

This project is part of the AirBnB clone series that aims to create a replica of the AirBnB platform. In this project, we have created a command-line interface that allows users to interact with the AirBnB clone application through the command line.

The command-line interface (CLI) for the AirBnB clone application is implemented in Python and provides a way for users to interact with the application using simple commands. The CLI allows users to create, update, delete, and retrieve data from the application's database. The data can be accessed and manipulated using the command-line interface, which provides a convenient way to interact with the application.

## Description of the command interpreter

The command interpreter is a command-line interface that allows users to interact with the AirBnB clone application. The command interpreter supports the following commands:

| Command | Description |
| --- | --- |
| help | Displays the list of available commands |
| quit | Exits the console |
| create | Creates a new instance of a class |
| show | Displays the details of an instance of a class |
| destroy | Deletes an instance of a class |
| all | Displays all instances of a class |
| update | Updates an instance of a class with new attributes |

The command interpreter supports the following classes:

| Class | Description |
| --- | --- |
| BaseModel | The base class for all classes in the AirBnB clone application |
| User | Represents a user in the AirBnB clone application |
| State | Represents a state in the AirBnB clone application |
| City | Represents a city in the AirBnB clone application |
| Amenity | Represents an amenity in the AirBnB clone application |
| Place | Represents a place in the AirBnB clone application |
| Review | Represents a review in the AirBnB clone application |

## How to start it

To start the command-line interface for the AirBnB clone application, follow these steps:

1. Clone the repository to your local machine:

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

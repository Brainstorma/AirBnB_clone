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

## File Descriptions
[console.py](console.py) - the console contains the entry point of the command interpreter. 
List of commands this console current supports:
* `EOF` - exits console 
* `quit` - exits console
* `<emptyline>` - overwrites default emptyline method and does nothing
* `create` - Creates a new instance of`BaseModel`, saves it (to the JSON file) and prints the id
* `destroy` - Deletes an instance based on the class name and id (save the change into the JSON file). 
* `show` - Prints the string representation of an instance based on the class name and id.
* `all` - Prints all string representation of all instances based or not on the class name. 
* `update` - Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file). 

#### `models/` directory contains classes used for this project:
[base_model.py](/models/base_model.py) - The BaseModel class from which future classes will be derived
* `def __init__(self, *args, **kwargs)` - Initialization of the base model
* `def __str__(self)` - String representation of the BaseModel class
* `def save(self)` - Updates the attribute `updated_at` with the current datetime
* `def to_dict(self)` - returns a dictionary containing all keys/values of the instance

Classes inherited from Base Model:
* [amenity.py](/models/amenity.py)
* [city.py](/models/city.py)
* [place.py](/models/place.py)
* [review.py](/models/review.py)
* [state.py](/models/state.py)
* [user.py](/models/user.py)

#### `/models/engine` directory contains File Storage class that handles JASON serialization and deserialization :
[file_storage.py](/models/engine/file_storage.py) - serializes instances to a JSON file & deserializes back to instances
* `def all(self)` - returns the dictionary __objects
* `def new(self, obj)` - sets in __objects the obj with key <obj class name>.id
* `def save(self)` - serializes __objects to the JSON file (path: __file_path)
* ` def reload(self)` -  deserializes the JSON file to __objects

#### `/tests` directory contains all unit test cases for this project:
[/test_models/test_base_model.py](/tests/test_models/test_base_model.py) - Contains the TestBaseModel and TestBaseModelDocs classes
TestBaseModelDocs class:
* `def setUpClass(cls)`- Set up for the doc tests
* `def test_pep8_conformance_base_model(self)` - Test that models/base_model.py conforms to PEP8
* `def test_pep8_conformance_test_base_model(self)` - Test that tests/test_models/test_base_model.py conforms to PEP8
* `def test_bm_module_docstring(self)` - Test for the base_model.py module docstring
* `def test_bm_class_docstring(self)` - Test for the BaseModel class docstring
* `def test_bm_func_docstrings(self)` - Test for the presence of docstrings in BaseModel methods

TestBaseModel class:
* `def test_is_base_model(self)` - Test that the instatiation of a BaseModel works
* `def test_created_at_instantiation(self)` - Test created_at is a pub. instance attribute of type datetime
* `def test_updated_at_instantiation(self)` - Test updated_at is a pub. instance attribute of type datetime
* `def test_diff_datetime_objs(self)` - Test that two BaseModel instances have different datetime objects

[/test_models/test_amenity.py](/tests/test_models/test_amenity.py) - Contains the TestAmenityDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_amenity(self)` - Test that models/amenity.py conforms to PEP8
* `def test_pep8_conformance_test_amenity(self)` - Test that tests/test_models/test_amenity.py conforms to PEP8
* `def test_amenity_module_docstring(self)` - Test for the amenity.py module docstring
* `def test_amenity_class_docstring(self)` - Test for the Amenity class docstring

[/test_models/test_city.py](/tests/test_models/test_city.py) - Contains the TestCityDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_city(self)` - Test that models/city.py conforms to PEP8
* `def test_pep8_conformance_test_city(self)` - Test that tests/test_models/test_city.py conforms to PEP8
* `def test_city_module_docstring(self)` - Test for the city.py module docstring
* `def test_city_class_docstring(self)` - Test for the City class docstring

[/test_models/test_file_storage.py](/tests/test_models/test_file_storage.py) - Contains the TestFileStorageDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_file_storage(self)` - Test that models/file_storage.py conforms to PEP8
* `def test_pep8_conformance_test_file_storage(self)` - Test that tests/test_models/test_file_storage.py conforms to PEP8
* `def test_file_storage_module_docstring(self)` - Test for the file_storage.py module docstring
* `def test_file_storage_class_docstring(self)` - Test for the FileStorage class docstring

[/test_models/test_place.py](/tests/test_models/test_place.py) - Contains the TestPlaceDoc class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_place(self)` - Test that models/place.py conforms to PEP8.
* `def test_pep8_conformance_test_place(self)` - Test that tests/test_models/test_place.py conforms to PEP8.
* `def test_place_module_docstring(self)` - Test for the place.py module docstring
* `def test_place_class_docstring(self)` - Test for the Place class docstring

[/test_models/test_review.py](/tests/test_models/test_review.py) - Contains the TestReviewDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_review(self)` - Test that models/review.py conforms to PEP8
* `def test_pep8_conformance_test_review(self)` - Test that tests/test_models/test_review.py conforms to PEP8
* `def test_review_module_docstring(self)` - Test for the review.py module docstring
* `def test_review_class_docstring(self)` - Test for the Review class docstring

[/test_models/state.py](/tests/test_models/test_state.py) - Contains the TestStateDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_state(self)` - Test that models/state.py conforms to PEP8
* `def test_pep8_conformance_test_state(self)` - Test that tests/test_models/test_state.py conforms to PEP8
* `def test_state_module_docstring(self)` - Test for the state.py module docstring
* `def test_state_class_docstring(self)` - Test for the State class docstring

[/test_models/user.py](/tests/test_models/test_user.py) - Contains the TestUserDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_user(self)` - Test that models/user.py conforms to PEP8
* `def test_pep8_conformance_test_user(self)` - Test that tests/test_models/test_user.py conforms to PEP8
* `def test_user_module_docstring(self)` - Test for the user.py module docstring
* `def test_user_class_docstring(self)` - Test for the User class docstring

You can also use any executable file or script in your PATH as a command.

## Installation

```bash
git clone https://github.com/brainstorma/AirBnB_clone.git
```

change to the `AirBnb` directory and run the command:

```bash
 ./console.py
```

### Execution

In interactive mode

```bash
$ ./console.py
(hbnb) help
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
(hbnb)
(hbnb) quit
$
```

in Non-interactive mode

```bash
$ echo "help" | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```

## Testing

All the test are defined in the `tests` folder.

### Documentation

* Modules:

```python
python3 -c 'print(__import__("my_module").__doc__)'
```

* Classes:

```python
python3 -c 'print(__import__("my_module").MyClass.__doc__)'
```

* Functions (inside and outside a class):

```python
python3 -c 'print(__import__("my_module").my_function.__doc__)'
```

and

```python
python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
```

### Python Unit Tests

* unittest module
* File extension ``` .py ```
* Files and folders star with ```test_```
* Organization:for ```models/base.py```, unit tests in: ```tests/test_models/test_base.py```
* Execution command: ```python3 -m unittest discover tests```
* or: ```python3 -m unittest tests/test_models/test_base.py```

### run test in interactive mode

```bash
echo "python3 -m unittest discover tests" | bash
```

### run test in non-interactive mode

To run the tests in non-interactive mode, and discover all the test, you can use the command:

```bash
python3 -m unittest discover tests
```


## Usage

* Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

* Use help to see the available commands:

```bash
(hbnb) help
Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
(hbnb)
```

* Quit the console:

```bash
(hbnb) quit
$
```

### Commands

> The commands are displayed in the following format *Command / usage / example with output*
* Create

> *Creates a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json.*
```bash
create <class>
```

```bash
(hbnb) create BaseModel
6cfb47c4-a434-4da7-ac03-2122624c3762
(hbnb)
```

* Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel 6cfb47c4-a434-4da7-ac03-2122624c3762
[BaseModel] (a) [BaseModel] (6cfb47c4-a434-4da7-ac03-2122624c3762) {'id': '6cfb47c4-a434-4da7-ac03-2122624c3762', 'created_at': datetime.datetime(2021, 11, 14, 3, 28, 45, 571360), 'updated_at': datetime.datetime(2021, 11, 14, 3, 28, 45, 571389)}
(hbnb)
```

* Destroy

> *Deletes an instance of a given class with a given ID.*
> *Update the file.json*
```bash
(hbnb) create User
0c98d2b8-7ffa-42b7-8009-d9d54b69a472
(hbnb) destroy User 0c98d2b8-7ffa-42b7-8009-d9d54b69a472
(hbnb) show User 0c98d2b8-7ffa-42b7-8009-d9d54b69a472
** no instance found **
(hbnb)
```

* all

> *Prints all string representation of all instances of a given class.*
> *If no class is passed, all classes are printed.*
```bash
(hbnb) create BaseModel
e45ddda9-eb80-4858-99a9-226d4f08a629
(hbnb) all BaseModel
["[BaseModel] (4c8f7ebc-257f-4ed1-b26b-e7aace459897) [BaseModel] (4c8f7ebc-257f-4ed1-b26b-e7aace459897) {'id': '4c8f7ebc-257f-4ed1-b26b-e7aace459897', 'created_at': datetime.datetime(2021, 11, 13, 22, 19, 19, 447155), 'updated_at': datetime.datetime(2021, 11, 13, 22, 19, 19, 447257), 'name': 'My First Model', 'my_number': 89}"]
["[BaseMode
```
* count
> *Prints the number of instances of a given class.*
```bash
(hbnb) create City
4e01c33e-2564-42c2-b61c-17e512898bad
(hbnb) create City
e952b772-80a5-41e9-b728-6bc4dc5c21b4
(hbnb) count City
2
(hbnb)
```
* update
> *Updates an instance based on the class name, id, and kwargs passed.*
> *Update the file.json*
```
## Authors
<details>
    <summary>Brainstorma</summary>
    <summary>Anabi Ansah</summary>
    <ul>
    <li><a href="https://www.github.com/brainstorma">Github</a></li>
    </ul>
</details>
## How to add Author file
`Bash script for generating the list of authors in git repo`
```
#!/bin/sh
git shortlog -se \
  | perl -spe 's/^\s+\d+\s+//' \
  | sed -e '/^CommitSyncScript.*$/d' \
  > AUTHORS
 
## Authors
 Brainstorma - [Github](https://github.com/brainstorma)
 Anabi Ansah - [Github](https://github.com/brainstorma)
 
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

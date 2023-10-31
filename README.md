# Airbnb Console - ALX Project
The Airbnb Console serves as the initial phase of the Holberton School's Airbnb project, designed to encompass fundamental concepts of higher-level programming. The primary objective of the Airbnb project is to ultimately deploy a server that emulates the Airbnb website (HBnB). This segment introduces a command interpreter to manage objects for the Airbnb (HBnB) website.

## Functionality of the Command Interpreter:
- Create new objects (e.g., User or Place)
- Retrieve objects from various sources, such as files and databases
- Perform operations on objects (e.g., count, compute statistics)
- Update attributes of objects
- Delete objects

## Table of Contents
- [Environment](#environment)
- [Installation](#installation)
- [File Descriptions](#file-descriptions)
- [Usage](#usage)
- [Examples of Use](#examples-of-use)
- [Bugs](#bugs)
- [Authors](#authors)
- [License](#license)

## Environment
This project is developed and tested on Ubuntu 14.04 LTS using Python 3.4.3.

## Installation
1. Clone this repository: `git clone https://github.com/alexaorrico/AirBnB_clone.git`
2. Navigate to the Airbnb directory: `cd AirBnB_clone`
3. Run Airbnb interactively: `./console` and enter commands
4. Run Airbnb non-interactively: `echo "<command>" | ./console.py`

## File Descriptions
- [console.py](console.py): The console is the entry point of the command interpreter. It supports the following commands:
  - `EOF`: Exits the console
  - `quit`: Exits the console
  - `<emptyline>`: Overwrites the default empty line method and does nothing
  - `create`: Creates a new instance of `BaseModel`, saves it to the JSON file, and prints the ID
  - `destroy`: Deletes an instance based on the class name and ID (saves the change into the JSON file)
  - `show`: Prints the string representation of an instance based on the class name and ID
  - `all`: Prints the string representation of all instances based on the class name
  - `update`: Updates an instance based on the class name and ID by adding or updating attributes (saves the change into the JSON file)

### Classes in the `/models/` directory:
- [base_model.py](/models/base_model.py): The BaseModel class serves as the foundation for future classes. It includes the following methods:
  - `__init__(self, *args, **kwargs)`: Initializes the base model
  - `__str__(self)`: Provides a string representation of the BaseModel class
  - `save(self)`: Updates the `updated_at` attribute with the current datetime
  - `to_dict(self)`: Returns a dictionary containing all keys and values of the instance

Classes derived from BaseModel:
- [amenity.py](/models/amenity.py)
- [city.py](/models/city.py)
- [place.py](/models/place.py)
- [review.py](/models/review.py)
- [state.py](/models/state.py)
- [user.py](/models/user.py)

### The `/models/engine` directory contains the File Storage class that handles JSON serialization and deserialization:
- [file_storage.py](/models/engine/file_storage.py): This class serializes instances to a JSON file and deserializes them back into instances. It includes the following methods:
  - `all(self)`: Returns the dictionary `__objects`
  - `new(self, obj)`: Sets `obj` with key `<obj class name>.id` in `__objects`
  - `save(self)`: Serializes `__objects` to the JSON file (path: `__file_path`)
  - `reload(self)`: Deserializes the JSON file to `__objects`

### The `/tests` directory contains all unit test cases for this project, including tests for each model class:
- [test_base_model.py](/tests/test_models/test_base_model.py): Contains the TestBaseModel and TestBaseModelDocs classes. These test classes ensure the functionality of the BaseModel class and its documentation.
- [test_amenity.py](/tests/test_models/test_amenity.py): Contains the TestAmenityDocs class, which tests the Amenity class and its documentation.
- [test_city.py](/tests/test_models/test_city.py): Contains the TestCityDocs class, which tests the City class and its documentation.
- [test_file_storage.py](/tests/test_models/test_file_storage.py): Contains the TestFileStorageDocs class, which tests the FileStorage class and its documentation.
- [test_place.py](/tests/test_models/test_place.py): Contains the TestPlaceDocs class, which tests the Place class and its documentation.
- [test_review.py](/tests/test_models/test_review.py): Contains the TestReviewDocs class, which tests the Review class and its documentation.
- [test_state.py](/tests/test_models/test_state.py): Contains the TestStateDocs class, which tests the State class and its documentation.
- [test_user.py](/tests/test_models/test_user.py): Contains the TestUserDocs class, which tests the User class and its documentation.

## Examples of Use
```bash
vagrantAirBnB_clone$./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) all BaseModel
[[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
** no instance found **
(hbnb) quit
```

## Bugs
No known bugs at this time.

## Authors
- Alexa Orrico

 - [Github](https://github.com/alexaorrico) / [Twitter](https://twitter.com/alexa_orrico)
- Jennifer Huang - [Github](https://github.com/jhuang10123) / [Twitter](https://twitter.com/earthtojhuang)
- Second part of Airbnb: Joann Vuong

## License
This project is in the public domain and has no copyright protection.
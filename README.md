# Python Script For Password Generation
## (Random Password Creation & Based on Condition)


[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Description

Here I am generating passwords which are more important parts of the security. Mainly the passwords are  either randomly generated or based on certain conditions. Here I have written the python script which includes two different scenarios. 

### Secnario - 1

The First option is to generate the password based on the requirements provided by the client. In which the requirements include how many alphabets, digits, special characters, and overall total length of the password are required.

### Secnario - 2

The second option is generating a random password based on the password length that we are providing. Here there is no other input required from the client-side. 

## Features

- Multiple options for the generation of password
- Easy to understand
- Easy to code

## Modules Used

### String 
- `string.ascii_letters` Concatenation of the ascii 
- `string.digits` The string ‘0123456789’.
- `string.punctuation` String of ASCII characters which are considered punctuation characters in the C locale.

### Random
- `choice` method returns a randomly selected element from the specified sequence. The sequence can be a string, a range, a list, a tuple or any other kind of sequence.
- `sample` function for random sampling, randomly picking more than one element from the list without repeating elements. It returns a list of unique items chosen randomly from the list, sequence, or set.


## Pre-Requests

- Basic Knowledge of python
- Need to install python3.

## Behind the code

```sh
import random
import string

alphabtes = string.ascii_letters
digits = string.digits
specialCharacters = string.punctuation

passwordChara = list(alphabtes + digits + specialCharacters)

def condition_random_password():
  length = input("Enter the Password Length: ")
  if int(length.isdigit()):
     alpha_count = input("Enter the Alphabtes Count in Password: " )
     if int(alpha_count.isdigit()):
        digits_count = input("Enter the Digits Count in Password: ")
        if int(digits_count.isdigit()):
            special_count = input("Enter the Special Characters Count: ")
            if int(special_count.isdigit()):
                    characters_count = int(alpha_count) + int(digits_count) + int(special_count)
                    if characters_count > int(length):
                        print("The entered Character Count is Greater than the total Password Length")
                        return
                    password = [] 
                    for i in range(int(alpha_count)):
                        password.append(random.choice(alphabtes))
                    for i in range(int(digits_count)):
                        password.append(random.choice(digits))
                    for i in range(int(special_count)):
                        password.append(random.choice(specialCharacters))
                    if characters_count < int(length):
                        random.shuffle(passwordChara)
                        for i in range(int(length) - characters_count):
                            password.append(random.choice(passwordChara))
                    print("".join(password))
            else:
              print("Enter a valid special count")
        else:
          print("Enter a valid digit count")
     else: 
       print('Enter a valid alpha count')
  else: 
    print("Enter a valid length")

def random_password():
  singlePassword = string.ascii_letters + string.digits + string.punctuation
  length = input("Enter the Password Length: ")
  if length.isdigit():
    print("".join(random.sample(singlePassword, int(length))))
  else:
    print("Please enter a valid length")

print("Please Select the below options \n ")
option = input("1 - Generating based on Conditions \n2 - Randomly Generating the Password \n Enter the Option: ")
if option == "1": 
  condition_random_password()
elif option == "2":
    random_password()
else:
  print("Invalid Option")
```

## User Instructions

```sh
sudo yum install git -y
sudo yum install python3
git clone https://github.com/ajish-antony/python-password-generator.git
cd python-password-generator
$ python3 password.py
```


## Script running Demonstration

### Secnario -1
```sh
$ python3 password.py
Please Select the below options

1 - Generating based on Conditions
2 - Randomly Generating the Password
 Enter the Option: 1
Enter the Password Length: 16
Enter the Alphabets Count in Password: 6
Enter the Digits Count in Password: 4
Enter the Special Characters Count: 5
UyqxYf4616.{%@.:
```

### Secnario - 2

```sh
python3 password.py
Please Select the below options

1 - Generating based on Conditions
2 - Randomly Generating the Password
 Enter the Option: 2
Enter the Password Length: 16
?@:W(=,e^Nto+%Au
```

## Conclusion

Here I have made use of the python code to generate the passwords in two different scenarios. It's a basic and common scenario in projects.



### ⚙️ Connect with Me

<p align="center">
<a href="mailto:ajishantony95@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/ajish-antony/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>

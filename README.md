# Beginner-Survey
import csv

print("☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒")
print("☒                                        ☑")
print("☑     The Programming Skills Survey      ☒")
print("☒                                        ☑")
print("☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒ ? ☑ ? ☒")
print("")
print("We would like to find out more about your programming interests and skills. Thank you for taking a few minutes to answer the following questions of our survey.")
print("")

# Question 1
name = input("1. What is your name? ")
# Presence Check

while name=="":
   print("You cannot provide an empty answer. Please try again!")
   name = input("What is your name? ")
   
# Complete the code here to ask and validate all 6 questions of the survey
# ...

# Question 2
email = input("2. What is your email address? ")
while '@' not in email:   
   print("Invalid email address. Please enter a valid email address. ")
   email = input("What is your email address? ")
   
# Question 3
years = int(input("3. How many years have you been programming? "))

while years < 1 :
   print("invalid input. Enter a positive number.")
   years = int(input("How many years have you been programming? "))

# Question 4

fav_language = input("4. What is your favourite programming language? " )
while fav_language not in ["Python", "Java", "C++", "JavaScript", "Other" ]:
    print("Invalid Repsonse. ")
    fav_language = input("What is your favourite programming language? " )

if fav_language == "Other":
    new_language = input("Enter the name of the language: ")
    fav_language = new_language
   

# Question 5
description = input("5. Describe your programming skills in no more than 10 characters: ")

while len(description) > 10:
   print("Too many characters. Characters should be no more than 10 characters.")
   description = input("Describe your programming skills in no more than 10 characters: ")
   
# Question 6
while True:
   rating = int(input("6. How would you rate your programming skills on a scale of 1 to 5? " ))
   if rating < 1 or rating > 5:
      print("Invalid number. Enter a number between 1 to 5 ")
   else:
      break

print("Thank you for answering the survey. ")


# Finally, add some code here to save the answers provided in the file called results.csv
# ...
with open('results.csv', mode='a', newline='') as file:
    writer = csv.writer(file)
    
    # Add header row if the file is empty
    if file.tell() == 0:
       writer.writerow(["Name", "Email", "Years of Programming", "Favorite Language", "Description", "Rating"])

    
    # Write the user responses as a new row
    writer.writerow([name, email, years, fav_language, description, rating])
    print("Data written successfully to 'results.csv'. ")


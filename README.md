# Final-Project_Flask-Application-Healthcare
## Web Development with Flask:
### Create a simple webpage using Flask to collect user data.(Ref : Geeks for Geeks, Youtube_TechwithTim )

# Install flask 'pip install flask'on git bash and then import flask 
pip install 
# On Visual Studio Code create a templates folder for the html file, then create a python file 
from flask import Flask, render_template, request
# Creating the app
app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/submit', methods=['POST'])
def submit():
    if request.method == 'POST':
        name = request.form['name']
        age = request.form['age']
        gender=request.form['gender']
        total_income=request.form['total_income']
        expense = request.form['expense']
        
        return render_template('success.html', name=name)  

if __name__ == '__main__':
    app.run(debug=True)

## Index. HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Data Collection</title>
</head>
<body>
    <h1>User Data Collection</h1>
    <form action="/submit" method="post">
        <label for="name">Name:</label><br>
        <input type="text" id="name" name="name" required><br>
        <label for="age">Age:</label><br>
        <input type="number" id="age" name="age" required><br>
        <label for="gender">Gender:</label><br>
        <input type="gender" id="gender" name="gender" required><br>
        <label for="total_income">Total_Income:</label><br>
        <input type="number" id="total_income" name="total_income" required><br>
        <label for="expense">Expense:</label><br>
        <input type="expense" id="expense" name="expense" required><br>

        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>

# Data Storage with MongoDB: ## New concept_ need to really get more understanding on it (Ref : Geeks for Geeks, Youtube_TechwithTim, chatgpt )
Pip Install MongoDB

from pymongo import MongoClient
client = MongoClient('mongodb://localhost:27017/')
db = client['userdata']
collection = db['users']

# Data Processing with Python or R:_ 
## Create a Python or R class named "User."_ Jupyter Notebook 

class User:
    def __init__(self, name, age, email, expense_categories):
        self.name = name
        self.age = age
        self.gender = gender
        self.total_income = total_income

    def process_data(self):
        # Add data processing logic here
        pass

import csv

def store_in_csv(users):
    with open('user_data.csv', 'w', newline='') as csvfile:
        fieldnames = ['Name', 'Age','Gender', 'Total_Income','Expense']
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)

        writer.writeheader()
        for user in users:
            writer.writerow({'Name': user.name, 'Age': user.age, 'Gender': user.gender, 'Total Income': user.total_income})

df = pd.read_csv('user_data.csv', encoding='utf-8')



## Challenges:

# The assignment was challenging since  there were many new concepts to learn and very limited time to really get to understand and be able to apply the same in the tasks provided.

# Data Visualization: I was not able to perform the data visualization as i ran out of time 
# Deployment on AWS: I was able to set up signup for an account with AWS but could not figure out how to really deploy my flask application . Still working on it.


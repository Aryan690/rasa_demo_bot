# Chatbot using Rasa-X (OS: Ubuntu)
Let's build a chatbot using Rasa, one of the most popular open-source libraray base don NLU. Here we are using Ubuntu but you can do that in any of the operating system.

#H3 Install the Rasa in your system
You can easily install the rasa open-source by going through the below codes easily but if you still have any doubt, please checkout the official [Rasa installation guide](https://rasa.com/docs/rasa/installation/)
First you need to make sure, you have pip and python modules installed
```
python3 --version
pip3 --version
```
If these packages are already installed, these commands should display version numbers for each step, and you can skip to the next step.
Otherwise, proceed with the instructions below to install them.
```
sudo apt update
sudo apt install python3-dev python3-pip
```
Now you need to create new virtual environment by choosing a Python interpreter and making a `./venv` directory to hold it:
```
python3 -m venv ./venv
```
Activate the virtual environment
```
source ./venv/bin/activate
```
Now you are all set to install the Rasa in your system, we will install Rasa(full) to make sure we do not get any errors in future.
```
pip3 install rasa[full]
```
Sometimes our system libraries and dependencies ain't updated so we can just do by running the below command
```
sudo apt-get install libxml2-dev libxmlsec1-dev libxmlsec1-openssl
```

# Creating our first project
You are now ready to go! So what's next? You can create a new project by running:
```
rasa init
```
Run the above command in terminal and it'd ask you to specify the path where you want to create your first project. Make a new folder in your system and specify the path correctly.

# Interact with Rasa
As of now, you have created a project and when you create a new project with rasa, it comes with some of the pre-built intents, stories and domain. In simple terms, it can understand few of our commands.
```
rasa shell
```
Use this command, to start your bot working in the Ubuntu terminal and interact with it.

# Install Rasa-x
You can now install the Rasa-X. It provides you a GUI to work on your project easily and efficiently without recalling the commands on shell.
```
pip 3 install rasa-x --extra-index-url https://pypi.rasa.com/simple         
```
Once installed, you can start the Rasa-X by using the bwlow command and Rasa-X would open in your broswer's new tab.
```
rasa x
```

# Make a web-based widget
From the above steps, you are now familiar with creating different intents and adding various new commands in your bot. Now its time to build a widget of it so we can try it out. Here we will be hosting our bot on a local host to just test it out first but later on we can deploy it on heroku and generate an API.
- Since this Chat UI communicates with the Rasa server using `rest` channel, make sure you have added `rest` channel in the `credentials.yml` file
- Once you have developed your bot and you are ready to integrate the bot with the UI, you can start the Rasa server using the below command in the Shell
  ```
  rasa run -m models --enable-api --cors "*" 
  ```
Once you have you Rasa server up and running, you can test the bot by running the below command in your VS Code or in any IDE terminal.
```
python -m http.server
```
and go to the localhost in your web-browser.


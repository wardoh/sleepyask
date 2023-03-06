![image](https://user-images.githubusercontent.com/84760072/223039320-2eb3b41f-3981-448d-a899-52ee9cb63acd.png)

<p align="center">
  A small tool for automating collecting data from ChatGPT over long periods of time.
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/catppuccin/catppuccin/main/assets/palette/macchiato.png" width="400" />
</p>

<p align="center">
	<a href="https://github.com/hwelsters/sleepyask/stargazers">
		<img alt="Stargazers" src="https://img.shields.io/github/stars/hwelsters/sleepyask?style=for-the-badge&logo=starship&color=C9CBFF&logoColor=D9E0EE&labelColor=302D41"></a>
	<a href="https://github.com/hwelsters/sleepyask/releases/latest">
		<img alt="Releases" src="https://img.shields.io/github/release/hwelsters/sleepyask.svg?style=for-the-badge&logo=github&color=F2CDCD&logoColor=D9E0EE&labelColor=302D41"/></a>
	<a href="https://github.com/hwelsters/sleepyask/issues">
		<img alt="Issues" src="https://img.shields.io/github/issues/hwelsters/sleepyask?style=for-the-badge&logo=gitbook&color=B5E8E0&logoColor=D9E0EE&labelColor=302D41"></a>
</p>

# What does it do?
ChatGPT currently limits the number of questions that users may ask per hour. The goal of this project is to allow users to just leave their computers on for extended periods of time to collect large amounts of responses from ChatGPT. There might not be a lot of practical use for this. Its main use is in research or data analysis.

# Install as a Python Library
```
pip install sleepyask
```

![image](https://user-images.githubusercontent.com/84760072/223040760-e440fd82-9fa0-4869-9ea0-7028373752ee.png)

# Documentation

<details>
	<summary><h3>Using the Official ChatGPT API</h3></summary>
	
## Authentication
You are required to provide an organization as well as an API Key  
If you are not part of an organization, use this: org-PuBY7H2zebXAGmpU6YsRQ3c1  
Your create an API Key on OpenAI by 
```
clicking on your profile picture on the top-right > View API Keys > Create new secret key.  
```
Sample config
```python
config = {
	"organization": "Your OpenAI organization",
	"api_key": "Your OpenAI api key"
}
```
## Sample code
```python
from sleepyask.openai import chat

# Your ChatGPT login information
config_1 = {
	"organization": "Your ChatGPT organization",
	"api_key": "Your ChatGPT api key"
}

config_2 = {
	"organization": "Your ChatGPT organization",
	"api_key": "Your ChatGPT api key"
}

configs = [config_1, config_2]

# List of questions you would like to ask ChatGPT
question_list = [
  'What is 1 + 1?',
  'What is 1 + 2?',
  'What is 1 + 3?'
]

# The filename in which you would like your responses to be stored.
output_file_path = 'draw.json'  

# Run sleepy_ask
chat.ask(configs=configs,
           questions=question_list,
           output_file_path=output_file_path,
           verbose=True)
```
</details>

  
<details>
	<summary><h3>Using the Unofficial ChatGPT API</h3></summary>
	
## Authentication
There are multiple ways to configure authentication with ChatGPT:  
**Email + Password**  
```python
config = {
  "email": "Your ChatGPT email",
  "password": "Your ChatGPT password"
}
```  

**Access Token**  
Access token can be found here: https://chat.openai.com/api/auth/session
```python
config = {
  "access_token": "Your access token"
}
```

![image](https://user-images.githubusercontent.com/84760072/223040769-1f0a4e76-247f-444f-b6f7-4ea2e8addca4.png)

### Sleepyask supports the use of multiple accounts
You can use multiple accounts to collect responses at a significantly quicker rate.  
Example usage:
```python
from sleepyask.free import chat

# Your ChatGPT login information
config_1 = {
  "email": "Your ChatGPT email",
  "password": "Your ChatGPT password"
}

config_2 = {
  "email": "Your ChatGPT email",
  "password": "Your ChatGPT password"
}

configs = [config_1, config_2]

# List of questions you would like to ask ChatGPT
question_list = [
  'What is 1 + 1?',
  'What is 1 + 2?',
  'What is 1 + 3?'
]

# The filename in which you would like your responses to be stored.
output_file_path = 'draw.json'  

# Run sleepy_ask
chat.ask(configs=configs,
           questions=question_list,
           output_file_path=output_file_path,
           verbose=True)
```
</details>

# Get involved
- 🐛 **Found a bug or interested in adding a feature?** - Create an [issue][issue]  
- 🤗 **Want to help?** - Create a pull-request!  

[issue]: https://github.com/hwelsters/sleepyask/issues

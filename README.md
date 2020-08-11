# Covid-19-Tracker-ChatBot
A chatbot which gives updated details about covid19 spread all over India. This chatbot is made using RASA.It can answer your basic questions like "How are you?" and corona based questions like "Can you give me details of corona in Jharkhand?" More functionality coming soon...!!!

<h2>Installation </h2>
pip install rasa <br>
rasa init <br>

<h2>   Importent concepts:  </h2>

<b> Intent: </b>
Intent means purpose/aim/target of chatbot of the user input example, if user typed "I want to order a book?" here intent would be "ordering..." <br>

<b> Entity: </b>
useful information that can be extracted from user like, "I want to order a book?" from this we extract "book" as an entity. <br>

<b> Action : </b>
It is just a response from the chatbot so it can be a code reply or api response <br>

<b> Stories: </b>
These are a sample interaction between the user and bot, defined in terms of intents captured and actions performed.   <br>

<b> Domain:  </b>
Domain knowledge is required to reply for any user query.  <br>

We can define this all concepts in code as follows:
Intent and Entity ==> nlu.md
Story (Dialogue Management) ==> Stories.md
Actual output (Hard code)[all intent , action, response] ==> domain.yml
Custom reply ==> action.py

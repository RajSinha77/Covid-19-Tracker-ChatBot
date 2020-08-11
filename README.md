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


For covid19 chat bot we are using external opensource api https://api.covid19india.org/data.json following are the steps to build basic chatbot

Steps:
Edit nlu.md file and write intent

## intent:corona_status
- [india](state)
- [corona](state)
- [karnataka](state)
- [mumbai](state)
- [bihar](state)
- [delhi](state)
- [panjab](state)
- [asam](state)
- [andhra pradesh](state)
Edit stories.md file
## corona status path 
* corona_status
  - action_corona_status

Edit domain.yml and add action
actions:
  - action_corona_status
  - action_hello_world
  - action_search_restaurant
Edit action.py
class ActionCoronaTracker(Action):

    def name(self) -> Text:
        return "action_corona_status"

    def run(self, dispatcher: CollectingDispatcher,
            tracker: Tracker,
            domain: Dict[Text, Any]) -> List[Dict[Text, Any]]:
        
        response = requests.get('https://api.covid19india.org/data.json').json()

        entities = tracker.latest_message['entities']
        state=None
        message = "Active cases are {0}\n, confirmed cases are {1}\n, Total deaths are {2}\n, Total patient recovered are {3}\n"
        for e in entities:
            if e['entity'] == 'state':
                state=e['value']
            for data in response["statewise"]:
                if data['state']==state.title():
                    
                    message = message.format(data['active'], data['confirmed'],data['deaths'],data['recovered'])

                else:
                    message = "Sorry data not available for input: {}".format(state)
            
        dispatcher.utter_message(text=message)

        return []
        
<b>To run server </b> <br>
    sudo rasa run actions
<b>To run shell </b>  <br>
    sudo rasa shell

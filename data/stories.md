## happy path
* greet
  - utter_greet
* mood_great
  - utter_happy
  
## what is corona
* corona_intro
  - utter_corona_intro

## about1
* covid
 - utter_covid
  
## sad path 1
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* affirm
  - utter_happy

## sad path 2
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* deny
  - utter_goodbye

## say goodbye
* goodbye
  - utter_goodbye

## bot challenge
* bot_challenge
  
## about symptoms
* symptoms
  - utter_ans_sym
  - utter_name
* my_name{"NAME":"raj"}
  - slot{"NAME":"raj"}
  - action_your_name
 
## state_data_with_district
* state{"user_state":"Jharkhand","user_district":"Ranchi"}
  - slot{"user_state":"Jharkhand","user_district":"Ranchi"}
  - action_total_cases
  - utter_email
* my_email{"email_id":"rajsinha.bit@gmail.com"}
  - slot{"email_id":"rajsinha.bit@gmail.com"}
  - utter_mobile
* my_number{"mob_no":"8504897797"}
  - slot{"mob_no":"8504897797"}
  - utter_information
  - action_email_sent
  
## state_data
* how_many_cases{"iso_state":"KA"}
  - slot{"iso_state":"KA"}
  - action_total_cases_in_state
  - utter_email
* my_email{"email_id":"rajsinha.bit@gmail.com"}
  - slot{"email_id":"rajsinha.bit@gmail.com"}
  - utter_mobile{"mob_no":"8504897797"}
  - slot{"mob_no":"8504897797"}
* my_number
  - utter_information
  - action_email_sent
 
## loction_is_not_provided
* location_provider
  - utter_location_enter
* dont_know_anything
  - utter_details_inlink
  - utter_did_that_help1

 
## about_graphics
* graph
 - utter_india_map
* world_map
 - utter_covid_map
 
## about_how_are_you
* fine
 - utter_iamabot

 
## dont_provide
* dont_provide
 - utter_provide_info
 
## full_statename_provided
* full_statewise{"user_state":"Jharkhand"}
 - slot{"user_state":"Jharkhand"}
 - action_cases_in_state
 - utter_email
* my_email{"email_id":"rajsinha.bit.com"}
  - slot{"email_id":"rajsinha.bit@gmail.com"}
  - utter_mobile
* my_number{"mob_no":"8504897797"}
  - slot{"mob_no":"8504897797"}
  - utter_information
  - action_email_sent
  
## helpline_provide
* helpline_number{"user_state":"Jharkhand"}
 - slot{"user_state":"Jharkhand"}
 - action_helpline
 
## video_provide
* video
 - utter_video_src
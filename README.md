# Night Porter Bot
This is a submission for Google's global Dialogflow CX competition (August 2021).
It contains an agent with one flow to be imported into Dialogflow CX.

The agent currently only knows these demo entries:
- "Club XMPL" in Los Angeles
- "The MVP" in Seattle
- "The Source" in New York City

## Description
This is the very first small step to build a bot that can assist with COVID-related information about night life activities.

### The Issue
During the pandemic not only many businesses and shops had to discontinue their service, but also all kinds of cultural institutions and night life venues have been closed down.
Now people and culture are striving to claim back their life. But the information about what activities are possible in which venues under which conditions is scattered all around or not available in the web at all.

People are looking for an easily accessible service in order to get reliable information about specific venues and questions like:
- is club XYZ still shut down? What are the opening hours now?
- do I have to make a reservation or book a ticket in advance?
- what are the official policies for the kind of venue in that city?
- what are the specific additional policies of this venue?

An additional feature could be to offer recommendations based on the requirements of the people.

### Systems Design
The vision of a complete system would be like this:

*Bot Tier*
- Dialogflow CX
- Frontend integration in Dialogflow Messenger, Facebook Messenger and Websites
- Integration with Backend Services using Webhooks

*Backend Service Tier*
- Look-up Service --> parse venue names from chat request and look up latest info of that specific venue
- Recommender Service

*Data Tier*
- Official COVID policies (structured by city and type of venue, ingested from official sources)
- Venue data (to be edited by venue managers)

Maybe venue data (like address, contact information and additional COVID policies) could be created by utilizing Google My Business, otherwise a new service for managing the data has to be created as well.

## Current State
Currently the bot is only existing as a flow in Dialogflow CX. The static demo content is delivered by a conditional response.

## TODO / Next Tasks
- Design supplemental intents handling for FAQ like: how reliable is the information?
- Create Look-Up Backend Service
- Replace conditional response with webhook of Look-Up Service
- Deliver the lengthy information as a downloadable PDF in the chat for later offline use
- Organize ingestion of official COVID policies
- Create venue database (and mgmt service)

## How to improve
- Test and improve recognition of city names
- Analyze chat logs in order to identify problems
- Identify most requested venues that are not found in database

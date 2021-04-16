# Chatbots

## Rasa framework

### Training Data

#### NLU training data

- structured information about user messages

#### Conversation training data

- stories and rules
- representations of conversations

##### Stories

- used for training an ML model to
	- identify patterns
	- generalize unseen conversation paths

##### Rules

- small pieces of conversations that should always follow the same path

### Domain

- the universe of the chatbot
- can be defined in multiple files

#### Intents

- lists all intents used your NLU data (nlu.yml)

#### Entites

- lists all entities that can be extracted in the NLU pipeline

#### Slots

- the bot's memory
- key-value store

#### Responses

- messages that the bot sends to the users
- slots can be used to fill out variables `{name}`

#### Forms

- a special type of action
- for collecting information form the user

#### Actions

- things a bot can do
- e.g. respond to a user, external API call, query a database

#### Cnfig

- maintains `store_entities_as_slots` parameter 

### Config

#### DIETClassifier

- Dual Intent Entity Transformer
- intent classification and entity extraction

#### TED Policy

- Transfer Embedding Dialogue
- next action prediction and entity recognition

# VISHAL AI BOT
### IKY (I Know You) AI Chatbot framework built in Python

Building a chatbot can sound daunting, but it’s totally doable. IKY is an AI powered conversational dialog interface built in Python. With IKY it’s easy to create Natural Language conversational scenarios with no coding efforts whatsoever. The smooth UI makes it effortless to create and train conversations to the bot and it continuously gets smarter as it learns from conversations it has with people. IKY can live on any channel of your choice (such as Messenger, Slack etc.) by integrating it’s API with that platform.

You don’t need to be an expert at artificial intelligence to create an awesome chatbot that has artificial intelligence. With this basic project you can create an artificial intelligence powered chatting machine in no time.There may be scores of bugs. So feel free to contribute  via pull requests.

![](https://image.ibb.co/eMJ9Wx/Screen_Shot_2018_04_28_at_1_45_28_PM.png)

### Installation

### Using docker-compose (Recommended) 
```sh
docker-compose build
docker-compose up -d
docker-compose exec iky_backend python manage.py init
```

### Using Docker
```sh

# build docker images
docker build -t iky_backend:2.0.0 .
docker build -t iky_gateway:2.0.0 frontend/.

# start a mongodb server
docker run --name mongodb -d mongo:3.6

# start iky backend
docker run --name=iky_backend --link mongodb:mongodb -e="APPLICATION_ENV=Production" iky_backend:2.0.0

# setup default intents
docker exec -it iky_backend python manage.py init

# start iky gateway with frontend
docker run --name=iky_gateway --link iky_backend:iky_backend -p 8080:80 iky_gateway:2.0.0

```

### without docker

#### backend

* Setup Virtualenv and install python requirements
```sh
make setup

make run_dev

source venv/bin/activate && python manage.py init
```
* Production
```sh
make run_prod
```

#### frontend
* Development
```sh
cd frontend
npm install
ng serve
```
* Production
```sh
cd frontend
ng build --prod --environment=python
```
serve files in dist/ folder using nginx or any webserver

### Heroku
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

* add your dev/production configurations in config.py

### DB

#### Restore
You can import some default intents using follwing steps

- goto http://localhost:8080/agent/default/settings
- click 'choose file'
- choose 'examples/default_intents.json file'
- click import

### Screenshots

![](https://i.ibb.co/4f8x6Ws/Screen-Shot-2018-04-28-at-1-38-15-PM.png)
---
![](https://i.ibb.co/YZjk3Ty/Image-3836.png)
---
![](https://i.ibb.co/z2bvtL4/Image-3857.png)
---
![](https://i.ibb.co/f871qv2/Image-4306.png)
### Tutorial

Checkout this basic tutorial on youtube,

#Soon creating the Video tutorial for the program installation and usage


Watch tutorial on [Fullfilling your Chatbot Intent with an API Call - Recipe Search Bot](https://www.youtube.com/watch?v=gqO69ojLobQ)

[Chatbot in action comming soon] {}

### To-do List
 *  Write Unit Tests
 *  PEP-8 compliance
 *  Word2Vec Integration
 *  NLTK to Spacy migration
 *  PyCRFSuite to sklearn-crfsuite migration
 *  Support follow up conversations
 
 ### Dependencies documentations
* [NLTK documentation](www.nltk.org/)
* [SKLearn documentation](http://scikit-learn.org/)
* [CRFsuite documentation](http://www.chokkan.org/software/crfsuite/)
* [python CRfSuite](https://python-crfsuite.readthedocs.io/en/latest/)

**Free Program, And always for you Friends **
<hr></hr>

_In God we Trust 😇 , and Rest is Data 📊_.

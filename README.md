# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

### Docker setup
Follow these steps to deploy the Todo App on your local machine or on the Google Cloud Platform.

Prerequisites
Docker installed on your machine.
Git is installed on your machine.
Python is installed on your machine.
Installation

```bash
$ sudo apt install docker.io
```

```bash
$ vim Dockerfile
```
In the docker file write : 

  FROM python:3
  RUN pip install django==3.2

  COPY . .

  RUN python manage.py migrate

  CMD ["python","manage.py","runserver","0.0.0.0:5050"]


Back to the console:  
```bash
$ sudo docker build . -t todo_app
```

###  Docker Deploy on the Google Cloud Platform done

###  Now use Jenkins for CD(Continious Delivery)


```bash
    	sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  	https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
    	echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  	https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  	/etc/apt/sources.list.d/jenkins.list > /dev/null
  	sudo apt-get update
	sudo apt-get install jenkins

  	sudo systemctl enable jenkins

	sudo systemctl start jenkins

	sudo systemctl status jenkins





```


Jenkins port ids 8080.

You need to open an account in jenkins

Now open a free styleproject in jenkins and add build command
	Building steps commands in the jenkins:
```bash
	cd /home/oshayer_siddique2001/django-todo
	sudo -S docker build . -t tododev
	sudo -S docker run -d -p 5050:5050 tododev

	
```
### Continuous Delivery is Done


### NOW integrate with GitHub with a Personal Access token and make an actual CI/CD pipeline


set up a new freestyle project and do plugins with Jenkins and set ups PSA then write the build command:
	
```bash
	sudo -S docker build . -t todoappcicd
	sudo -S docker run -d -p 5050:5050 todoappcicd



	
```



 

https://github.com/Oshayer-Siddique/django-todo-ci-cd/issues/1#issue-2061669695










  

  




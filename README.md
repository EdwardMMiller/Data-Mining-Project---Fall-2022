# Data Mining Fall 2022 CUNY Graduate Center 

- See Project details found in attached notebook 

[requirements.txt](https://github.com/EdwardMMiller/Data-Mining-Project---Fall-2022/files/10222333/requirements.txt)

INSTRUCTIONS TO CREATE DOCKERFILE

when docker is running go to working directory

Type in terminal - 

cd - 
# change to the directory containing dockerfiles

touch Dockerfile 
### IMPORTANT TO DO IT LIKE THIS - use touch command, making a new text file causes errors

Go to newly created Dockerfile and copy this 

FROM python:3.9.12

EXPOSE 8501

WORKDIR /app

COPY . .

RUN pip3 install -r requirements.txt

ENTRYPOINT ["streamlit", "run", "News_Classifier_App.py", "--server.port=8501", "--server.address=0.0.0.0"]

Type in Terminal -

docker build -t news_classifier_app . ### IMPORTANT - DON"T LEAVE OFF THE DOT AT THE END OF THIS COMMAND!

docker run -p 8501:8501 news_classifier_app

http://localhost:8501

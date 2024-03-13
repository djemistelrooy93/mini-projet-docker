FROM python:3.8-buster
LABEL maintainer="djemil.aitsahel@gmail.com for bootcamp devops eazytraining"
EXPOSE 5000
COPY ./requirements.txt /
COPY ./student_age.py /
#COPY ./student_age.json /data/student_age.json
VOLUME /data
RUN apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
RUN pip3 install -r /requirements.txt
CMD [ "python", "./student_age.py" ]

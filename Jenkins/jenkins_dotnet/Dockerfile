FROM jenkins/jenkins:2.453-jdk17
USER root
RUN apt-get update && apt-get install wget
RUN . /etc/os-release && wget https://packages.microsoft.com/config/$ID/$VERSION_ID/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN dpkg -i packages-microsoft-prod.deb
RUN rm packages-microsoft-prod.deb
RUN apt-get update && apt-get install -y dotnet-sdk-6.0
RUN wget https://github.com/allure-framework/allure2/releases/download/2.28.0/allure-2.28.0.tgz && tar -xf allure-2.28.0.tgz
RUN rm allure-2.28.0.tgz 
RUN ln -s /allure-2.28.0/bin/allure /usr/bin/allure
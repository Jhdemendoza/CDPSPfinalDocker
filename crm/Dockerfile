FROM ubuntu:16.04
RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get update
RUN apt-get install -y nodejs
RUN git clone https://github.com/CORE-UPM/CRM_2017.git
WORKDIR CRM_2017
RUN git clone https://github.com/vishnubob/wait-for-it.git
ENV DATABASE_URL=postgres://crm:xxxx@db:5432/crm
RUN npm install
EXPOSE 3000
CMD npm run-script migrate_local; npm run-script seed_local; npm run-script supervisor

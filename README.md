### DOCKER-PKI
Creation of a pki in a docker infrastructure with an nginx reverse-proxy

## HOW IT WORKS

This mini pki infrastructure is a projet that certificates connections with clients certificates generated with de CA authority. 

## RUN THE PROJECT

* Clone the projet on your desktop. 
* Insure that you have [docker](https://docs.docker.com/engine/install/) and [docker-compose](https://docs.docker.com/compose/install/) installed on your computer 
* Add this line in you `/etc/hosts` : `pki.fredericpinaud.fr 127.0.0.1`
* Go on the project folder you pull
* Execute the run command: `docker-compose up -d`
* Go on your browser and go to `pki.fredericpinaud.fr`

## CHECK THAT PKI WORKS

In you brwoser you should have a window saying that yhe connection might not be secure because the certificate is not validated by a know authority.
To change that, you have to import the client certificate present in this project. 

Go in your Mozilla Firefox (in french) "Préférences/Vie Privée et sécurité/Afficher les certificats/Autorités" then "Importer" and select the `ca.der` present in the `certificates` folder of the project.

Refresh the page of `pki.fredericpinaud.fr`, the security warning should disappear. Your connection is authenticated with the authority added in the brwoser list. Congrats !
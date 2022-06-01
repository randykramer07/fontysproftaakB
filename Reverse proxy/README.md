# Reverse proxy

We hebben een reverse proxy opgezet. De reverse proxy zorgt ervoor dat alle aanvragen die op de router binnen komen naar de goede server worden gestuurd. Dat gaat door middel van een poort forwarden in de router naar de reverse proxy server. Wij hebben daar poort 80 voor gebruikt en daarom luistert de reverse proxy server ook op poort 80. Als je een aanvraag doet op hanskazan.space ga je via de reverse proxy naar de webserver. Zo gaat dat ook met de andere aanvragen op ons domein.


Voor de websocket zijn speciale regels toegevoegd aan de config file. Op die manier kan alle data dat komt kijken bij een websocket connectie goed door de reverse proxy heen lopen. 


We hebben eerst Nginx geïnstalleerd op een server:

```sudo apt install nginx```


Schakel de standaard configuratie van Nginx uit:

```unlink /etc/nginx/sites-enabled/default```

Maak een reverse proxy configuration file aan:

```cd /etc/nginx/sites-available```

```sudo nano example.conf```


Activeer het bestand:


```sudo ln -s /etc/nginx/sites-available/example.conf /etc/nginx/sites-enabled/```


Test het bestand: 

```sudo nginx -t```

En dan start je hem opnieuw op om te zorgen dat hij het goed doet:

```sudo systemctl restart nginx```

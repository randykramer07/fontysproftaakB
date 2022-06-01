# Website 

We hebben een simpele apache webpagina opgezet. Als je hanskazan.space opzoekt wordt je door de reverse proxy doorgestuurd naar de ip van de VM waar de webpagina op draait. 


# Hoe hebben we het opgezet? 

We hebben als eerst een Ubuntu vm gemaakt. Hier hebben we door de volgende commando apache op geïnstalleerd: 


sudo apt update 

```sudo apt install apache2```

hierna is apache geinstalleerd en kun je de firewall poorten aanpassen. Je kunt kijken welke poorten je open kunt zetten door de onderstaande code 

sudo ufw app list 

Nu gaan we met de onderstaande code alle poorten voor apache open zetten. 

sudo ufw allow 'Apache' 

Hierna kun je controleren of het de poorten openstaan met het volgende. 

sudo ufw status 

Om te kijken of de apache server goed draait heb je de volgende code. 

sudo systemctl status apache2 

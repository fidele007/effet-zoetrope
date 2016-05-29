#Effet trombinoscope avec Arduino
Pour le projet final de ANU (Art Numérique), j'ai tenté de simuler l'effet trombinoscope en utilisant Arduino, un moteur et un LED.

##Pièces nécessaires:
- Un moteur (*j'ai utilisé un moteur DC à 3.3V*)
- Un LED
- Un Arduino

##Instructions
1. **Construire le modèle des images d'animation :** dans mon cas, j'ai trouvé un modèle de papier via le site http://www.korthalsaltes.com/ pour faire un [prisme octagonal](http://www.korthalsaltes.com/model.php?name_en=octagonal%20prism) dont chaque côté contient une image de l'animation.
2. **Montage :** c'est à vous de jouer pour monter un assemblage assez rigoureux pour facilement faire tourner le moteur et soutenir le modèle d'images. Voici le montage complète : ![Montage complet](https://github.com/fidele007/effet-trombinoscope/raw/master/montage.jpg)
3. **Arduino :** maintenant c'est la partie vraiment délicate dans ce projet. Voici le code que j'ai utilisé :

```{cpp}
int motorPin = 9;
int ledPin = 6;
int time = 5;
void setup() {
  pinMode(motorPin, OUTPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  time++;;

  // Set motor speed (between 0 and 255)
  analogWrite(motorPin, 90);

  // Blink the LED
  digitalWrite(6, HIGH);
  delayMicroseconds(time);
  digitalWrite(6, LOW);
  delayMicroseconds(time);
}
```

**NB:** L'important ici est de pouvoir contrôler, avec Arduino, la vitesse de moteur de manière que l'on peut voir l'animation. Malheureusement, jusqu'à la fin du projet je n'ai pas pu trouver la bonne méthode pour gérer la vitesse de moteur. Il faut savoir aussi qu'une valeur initiale de vitesse très faible n'est peut-être pas assez puissante pour faire tourner le moteur.

##Résultat :
Malgré mes efforts, je ne suis toujours pas arrivé à voir l'animation très bien. Par contre, on la voit mieux en vidéo.

Lien vers la vidéo de démonstration : https://vimeo.com/168565228

La vidéo est prise en 240ips.
---
## Poubelle-automatique

#### Ce projet permet d'ouvrir automatiquement le couvercle d'une poubelle.
---

---
# vidéo du montage
[![video](https://drive.google.com/open?id=1KCSdqdoHjAakh4zJk2HxLCmZ20t8hNeA)
---

# Montage

![SCHEMA](Schema-poubelle-automatique_bb.jpg)
---

# le code arduino

``` c++

#include <Servo.h>
#include <HCSR04.h>

Servo servoMotor;
UltraSonicDistanceSensor distanceSensor (6,5);

void setup() {
  Serial.begin(9600);
  servoMotor.attach(3);

}

void loop() {
  double distance = distanceSensor.measureDistanceCm();
  Serial.println(distance);


if(distance < 30 && distance>0) {
  
  servoMotor.write(80);
  delay (5000);
  } else {
  servoMotor.write(10);
}
}
```

---

# Bibliothéques



[capteur HC-SR04](https://www.amazon.fr/junkai-t%C3%A9l%C3%A9m%C3%A9trie-ultrasons-Distance-ultrasonique/dp/B07K14XXWQ/ref=sr_1_3?s=industrial&ie=UTF8&qid=1548842913&sr=1-3&keywords=HCSR04)

[servo SG90](https://www.amazon.fr/Longruner-Moteur-H%C3%A9licopt%C3%A8re-Bateau-robots/dp/B07236KYVC/ref=sr_1_1?ie=UTF8&qid=1548843579&sr=8-1&keywords=servomoteur+arduino)

---

# Liste des composants

[planche à pain](https://www.amazon.fr/Hilitand-Planche-Prototype-Soudure-Plastique/dp/B07GZJBDCP/ref=sr_1_3?s=computers&ie=UTF8&qid=1548257336&sr=1-3&keywords=planche+pain)

[arduino](https://www.amazon.fr/Classic-R3-Atmega328-compatible-Arduino-Robotdyn/dp/B06XR72KF2/ref=sr_1_1?ie=UTF8&qid=1548845793&sr=8-1&keywords=carte+nano+ordinateur+classic+arduino+uno+r3)

[servo SG90](https://www.amazon.fr/Longruner-Moteur-H%C3%A9licopt%C3%A8re-Bateau-robots/dp/B072J59PKZ/ref=sr_1_3?ie=UTF8&qid=1548845825&sr=8-3&keywords=servo+SG90)

[capteur HC-SR04](https://www.amazon.fr/ultrasons-HC-SR04-Capteur-distance-Arduino/dp/B00BIZQWYE/ref=sr_1_1?ie=UTF8&qid=1548845865&sr=8-1&keywords=capteur+HC-SR04)

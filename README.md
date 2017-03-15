# One time pad

Le *One Time Pad* (OTP) aussi appelé *masque jetable* est une technique simple mais sûr.

A ne pas confondre avec le One Time Password.

## Concepte

L'OTP est une technique de cryptographie qui ne peut pas être crackée mais qui requiert l'utilisation d'une clé partagée à utilisation unique de la même longeur que le message à envoyer.

La clé est aussi appelée *pad* ou *masque*.

Chaque bit/octet du message est chiffré en le combinant avec le bit/octet correspondant de la clé secrète (*one-time pad*) en utilisation l'addition modulaire (*A + B mod C*).

### Exemple

+ Message : taille **n** octet
+ Pad : taille **n** octet aléatoire
+ Alphabet : taille **x**
+ Chiffrement : `(message + clé) mod 26`
+ Déchiffrement : `(message - clé) mod 26`

![](src/otp-Diagram.svg)

Chiffrement :

```
07 (H)  04 (E)  11 (L)  11 (L)  14 (O)  message
+
23 (X)  12 (M)  02 (C)  10 (K)  11 (L)  key
=
30      16      13      21      25      message + key
=
04 (E)  16 (Q)  13 (N)  21 (V)  25 (Z)  (message + key) mod 26
```

Déchiffrement :



### Tentative de Cryptanalyse

## Confidentialité parfaite

## Histoire

D'abord décrit par Frank Miler en 1882 pour sécuriser le télégraphe, l'OTP a été ré-inventé en 1917. Le 22 juillet 1919, un brevet états-uniens a été déposé apr Gilbert Vernam sur l'opération XOR utilisée pour le chiffrement d'OTP.

L'OTP est un dérivé du chiffrement de Vernam mais la forme originelle du chiffrement de Vernam était vulnérable car la clé était répétée en boucle.

Le mot *pad* vient des premières implémentations où le support des clés était des bloc-notes (*pad of paper*).

## Problèmes

### Distribution des clefs

### Authentification

One-time-pad ne propose pas de service d'authentification.
Des méthodes d'authentification classiques peuvent êtres utilisées en plus de one-time-pad:

- MAC: Code d'authentification de message (Semblable au hash du message (message+clef secrete)
- Hashage classiqe
- Russian copulation (Réarrangement de message)

Cependant ces techniques d'authentification ne dispose pas de la qualité d'être parfaitement sûres comme one-time-pad.

### Véritable aléa

## Cas d'utilisations

### Applicabilité

### Utilisations historiques

One-time-pad est connu pour avoir été utilisé, depuis les années 1900, pour les communications spéciales des états:

- Pour les échanges diplomatiques (Dès 1923 en Allemagne, Téléphone rouge Washington-Moscou)
- Par les services secrets (agents secrets) 
- Par les forces spéciales
- Implémenté sous forme de machines à ruban perforés (notamment durant la seocnde guerre mondiale)

![Noreen machine](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Noreen.jpg/1280px-Noreen.jpg)

### Exploitations

+ Many Time Pad Attack – Crib Drag

## Sources

[Wikipedia](https://en.wikipedia.org/wiki/One-time_pad)
[Wikipedia](https://en.wikipedia.org/wiki/Authentication)
[Wikipedia](https://en.wikipedia.org/wiki/Russian_copulation)
[Wikipedia](https://en.wikipedia.org/wiki/Universal_hashing)

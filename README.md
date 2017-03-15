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
23 (X)  12 (M)  02 (C)  10 (K)  11 (L)  clé
=
30      16      13      21      25      message + clé
=
04 (E)  16 (Q)  13 (N)  21 (V)  25 (Z)  (message + clé) mod 26
```

Déchiffrement :

```
004 (E) 16 (Q)  13 (N)  21 (V)  25 (Z)  texte chiffré
-
023 (X) 12 (M)  02 (C)  10 (K)  11 (L)  clé
=
-19     4       11      11      14      texte chiffré - clé
=
007 (H) 04 (E)  11 (L)  11 (L)  14 (O)  message
```

### Tentative de Cryptanalyse

+ Texte chiffré : `EQNVZ`
+ Clé n°1 : `XMCKL` -> message n°1 : `HELLO`
+ Clé n°2 : `TQURI` -> message n°2 : `LATER`

Si un attaquant possède un temps infini et qu'il peut essayer toutes les combinaisons de clé possibles, il sera en mesure de trouvé plusieurs clés avec un message plausible.

En fait, il est possible de décrypté tous les messages possible avec le même nombre de charactères, mais il n'y a aucune information dans le texte permettant de choisir le bon message.

Dès que le message est grand, la clé étant de même taille, il devient impossible de tester toutes les possibilités (ex: clé de 50Mo), et le nombre de texte possible devient aussi démusérément grand.

## Confidentialité parfaite

## Histoire

D'abord décrit par Frank Miler en 1882 pour sécuriser le télégraphe, l'OTP a été ré-inventé en 1917. Le 22 juillet 1919, un brevet états-uniens a été déposé apr Gilbert Vernam sur l'opération XOR utilisée pour le chiffrement d'OTP.

L'OTP est un dérivé du chiffrement de Vernam mais la forme originelle du chiffrement de Vernam était vulnérable car la clé était répétée en boucle.

Le mot *pad* vient des premières implémentations où le support des clés était des bloc-notes (*pad of paper*).

## Problèmes

### Distribution des clefs

### Authentification

### Véritable aléa

## Cas d'utilisations

### Applicabilité

### Utilisations historiques

### Exploitations

+ Many Time Pad Attack – Crib Drag

## Sources

[Wikipedia](https://en.wikipedia.org/wiki/One-time_pad)

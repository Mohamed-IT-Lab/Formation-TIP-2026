# 🌐 Cours 01 : L'Adresse IP et le Masque (L'Identité)

Maintenant qu'on connaît le "Code de la route", voyons comment on donne une identité précise à chaque machine.

## 1. Qu'est-ce qu'une adresse IP ?
C'est l'adresse postale de votre ordinateur. Elle est composée de 4 nombres (ex: `192.168.1.10`).
* Elle doit être **unique** dans votre réseau local.

## 2. Le Masque de sous-réseau (Le séparateur)
C'est l'élément le plus important pour un technicien. Le masque sert à séparer l'adresse en deux parties :
1. **La partie RÉSEAU** (Le nom de votre rue / votre famille).
2. **La partie HÔTE** (Votre numéro de porte / votre identité).

### Exemple avec le masque standard `255.255.255.0` :
Si votre IP est `192.168.1.15` :
* Les **255** disent : "Regarde ces chiffres, c'est le nom de ton groupe". -> `192.168.1`
* Le **0** dit : "Ce chiffre-là, c'est ton numéro perso". -> `.15`

> **Règle d'or :** Pour se parler sans passer par un routeur, deux machines doivent avoir exactement la même partie "RÉSEAU".

## 3. Les Classes d'adresses
On choisit la classe selon la taille de l'entreprise :
* **Classe A** (`10.x.x.x`) : Pour les réseaux géants (Orange, Multinationales).
* **Classe B** (`172.16.x.x`) : Pour les universités ou grandes PME.
* **Classe C** (`192.168.1.x`) : Pour la maison et les petites boutiques.

---

## 🛠️ Application concrète (Le test du technicien)
Imagine deux PC dans une boutique :
* **PC 1 :** `192.168.1.10` | Masque : `255.255.255.0`
* **PC 2 :** `192.168.1.20` | Masque : `255.255.255.0`
* **PC 3 :** `192.168.2.30` | Masque : `255.255.255.0`

**Question :** Qui peut se parler ?
* **Réponse :** PC 1 et PC 2 sont dans la même rue (`192.168.1`). Ils se voient.
* PC 3 est dans une autre rue (`192.168.2`). Il est invisible pour les autres sans routeur !

---
*💡 Note de Mohamed : Si vous changez une box chez un client, vérifiez toujours qu'il n'avait pas d'IP fixes configurées sur ses imprimantes, sinon elles deviennent invisibles !*

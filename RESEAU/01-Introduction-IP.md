# Cours 01 : Introduction au Réseau

## Pourquoi et Comment ?

### 1. Le "Pourquoi" (L'utilité métier)
Dans une entreprise, le réseau sert à trois choses principales :
* **Partager** : Accéder à un serveur de fichiers ou une imprimante commune.
* **Communiquer** : Envoyer des mails, utiliser Teams ou accéder à Internet.
* **Sécuriser** : Faire en sorte que tout le monde n'ait pas accès à tout (ex: isoler Amel (secrétariat) de la salle de classe).

**Cas concret :** On t'appelle car un utilisateur ne peut plus imprimer. Si tu ne comprends pas le réseau, tu ne sais pas si c'est l'imprimante qui est en panne, le câble qui est débranché, ou si l'adresse IP a changé.

### 2. L'adresse IP : Votre "Identité" sur le réseau
Chaque machine a besoin d'une adresse unique. Une adresse IPv4 ressemble à ça : `192.168.1.15`.

**L'analogie de l'adresse postale** :
Pour qu'un courrier arrive, il faut deux informations dans l'adresse :
1. **Le nom de la rue** : C'est la partie **RÉSEAU**. Tous les gens d'une même rue partagent ce nom.
2. **Le numéro de la maison** : C'est la partie **HÔTE**. Il doit être unique dans la rue.

### 3. Le Masque de Sous-Réseau : Le "Séparateur"
C'est souvent là que les élèves bloquent. Le masque (ex: `255.255.255.0`) sert à dire à l'ordinateur : *"Où s'arrête le nom de la rue et où commence le numéro de maison ?"*

* **255** veut dire : "C'est le nom de la rue, on n'y touche pas".
* **0** veut dire : "C'est le numéro de la maison, on peut le changer".



**Exemple concret :**
* **IP** : `192.168.1` . `15`
* **Masque** : `255.255.255` . `0`
* **Résultat** : La rue s'appelle `192.168.1`. Tous les PC de cette rue doivent commencer par `192.168.1`.

### 4. Les 3 réglages de base
Pour qu'un PC communique, il lui faut obligatoirement ces trois informations :
1. **L'Adresse IP** : Le nom de la machine (ex: `192.168.1.15`).
2. **Le Masque** : Pour savoir dans quel réseau on est (ex: `255.255.255.0`).
3. **La Passerelle (Gateway)** : C'est l'adresse de la Box ou du Routeur. C'est la "porte de sortie" pour aller sur Internet. 

 **Définition** : Une passerelle est un élément matériel ou logiciel de réseau utilisé dans les réseaux de télécommunications qui permet aux données de circuler d'un réseau distinct à un autre.

### 5. Les Classes (La taille de l'entreprise)
On choisit la classe selon le nombre de machines dont on a besoin :

| Classe | Masque par défaut | Capacité (Nb de maisons) | Utilisation type |
| :--- | :--- | :--- | :--- |
| **Classe A** | `255.0.0.0` | 16 millions | Très grandes entreprises (Orange, IBM). |
| **Classe B** | `255.255.0.0` | 65 000 | Universités, grandes usines. |
| **Classe C** | `255.255.255.0` | 254 | PME, Maisons, Bureaux (Le plus courant). |



### Exercice de réflexion
Tu arrives dans une entreprise. Le PC a l'IP `192.168.1.10` et l'imprimante a l'IP `192.168.2.50`. Le masque est `255.255.255.0`. **Est-ce que ça va imprimer ?**

**Réponse :** Non, car ils ne sont pas dans la même 'rue' (l'un est dans la rue `192.168.1`, l'autre dans la rue `192.168.2`).



### Pratique : Voir ça "en vrai" sur ton PC
1. Touche **Windows + R**.
2. Taper **cmd** puis Entrée.
3. Taper **ipconfig**.

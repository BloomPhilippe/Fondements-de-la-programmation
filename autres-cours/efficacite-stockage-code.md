# Efficacité de stockage de code

Il faut bien comprendre que la rapidité d'une application dépends aussi du disque dur. 

Car tout type d'application est sur un disque, que ce soit sur un téléphone, sur un serveur, sur un ordinateur,...

Une application manipule des images, des vidéos, du texte particulier qui se trouve sur un disque donc il est logique de dire que nos performances dépendes aussi de lui, 

**Règles de bases :**

- Ne chargez que ce qui est nécessaire

    - Les lecture I/O sont équivalentes à des instances d'objets inutiles
    - Ne chargez pas des librairies que vous n'utiliserez pas.
    - Le code non utilisé prend quand même de la place en mémoire
    
- Lire ou écrire est susceptible de poser un problème

    - Privilégier un disque SSD pour stocker le programme

- Lorsqu'on écrit un gros volume, il vaut mieux découper en groupe (chunk)

    - Traiter partie par partie un fichier est préférable que de traiter l'ensemble du fichier d'un coup.
    

    






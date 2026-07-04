## Première connexion

Connectez-vous avec l'utilisateur/mot de passe YunoHost fourni à l'install. Ensuite, changez votre mot de passe depuis les paramètres propres à Youtarr si vous voulez qu'il diffère de celui utilisé pour amorcer le compte — il est indépendant de vos identifiants YunoHost et ne sera pas réinitialisé lors des mises à jour ou redémarrages.

## Stocker les téléchargements sur un stockage externe (ex. bibliothèque d'un serveur média)

Par défaut, Youtarr stocke les vidéos téléchargées dans son propre répertoire de données. Pour pointer vers un autre emplacement (montage NAS, bibliothèque d'une autre app...), allez dans le panel de configuration de l'app ("Stockage" > "Emplacement des téléchargements") et indiquez le chemin voulu.

Avant ça, assurez-vous que l'utilisateur système `youtarr` peut effectivement lire/écrire ce chemin — par exemple, si le répertoire cible appartient à un groupe (comme un groupe `multimedia` partagé utilisé par d'autres apps média sur votre serveur), ajoutez `youtarr` à ce groupe :

```
usermod -aG multimedia youtarr
systemctl restart youtarr
```

Sans ça, Youtarr échouera à écrire les fichiers téléchargés même si le chemin est correctement configuré.

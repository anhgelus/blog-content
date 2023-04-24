# 2023 - Présentation de mon setup fix

Et oui, comme tout véritable fan de FOSS et de tiling window manager, je ne pouvais pas vous faire une présentation plutôt complète de mon environnement de travail.

## Vue rapide

Commençons avec le plus simple : les specs :

**PC**

- Ryzen 5 3600
- RTX 2060 AORUS OC
- ASUS B450m Prime A II
- 250go de SSD Sata Kingston
- 1To HDD 7200tours/min
- 2x 500Go MX500 (SSD Sata)
- 500W Aerocool Maxpro (n'achetez pas ça) 
- 5x Arctic P12
- Ventirad AMD de base
- Case no name

**Autour**

- HyperX Alloy Origins (clavier)
- Logitech G502 (souris)
- ViewSonic XG2405-2 (Écran principal 23.8" IPS - 144Hz - 1ms)
- Iiyama ProLite XB2483HSU (Écran secondaire 23.8" VA matrix - 60Hz - 5ms)
- Sennheiser HD 400S (casque) avec câble changé car l'original est mort :(
- Corsair ST100 (support de casque)
- Behringer B2-Pro (micro)
- Focusrite Scarlett 2i2 3rd Gen (carte son externe)
- Pronomic MS-116 (Trépied pour micro)
- Vieux câble XLR
- Tapis de souris Amazon

**Software**

- EndeavourOS (OS principal)
[image neofetch]
- Windows 10 (OS secondaire)
- IDE :
    * Intellij IDEA (Java, Kotlin)
    * Goland (Golang)
    * PhpStorm (Web : html, css, scss, js, ts, php)
    * VIM (retouche rapide, markdown, yml)
    * Fleet (occasionnellement)

## Dual-boot

Beaucoup vont me demander "mais pourquoi tu as dual-boot Linux/Windows alors que WSL marche bien ?".

Ma réponse en 10 points :
- Linux est plus léger
- Linux consomme (beaucoup) moins de ressource que Windows + WSL (utile quand on a besoin de faire des tâches lourdes)
- Linux supporte bien mieux Docker (et Docker is life)
- Goland est beaucoup plus adapté pour du dev sous Linux, de même pour du dev en C/C++
- Meilleur support du SSH (important pour Git et pour l'administration système des différents VPS que j'utilise)
- Composer marche moins bien sous Windows (pour Laravel notamment)
- FOSS > closed source
- Je préfère l'idéologie libriste que celle de Microsoft
- La customisation est juste bien meilleur et bien plus simple sous Linux
- Bien plus ergonomique que sous Windows (le pouvoir des tilings wm)

Mais pourquoi je garde Windows alors ? Car bien que Proton permet de faire tourner de mieux en mieux les jeux sous Linux, ce n'est pas encore ça. J'ai bien plus de performance et moins d'input lag sous Windows. De plus, de nombreux anti-cheats empêchent le jeu de se lancer correctement sous Linux.

Quand j'aurais un PC plus puissant, je pourrais me libérer de Windows en créant une VM pour jouer.

## Configuration

Passage beaucoup plus technique et sûrement moins intéressant pour les néophytes mais bien configurer son système est important pour qu'il nous corresponde et pour qu'on puisse gagner en rapidité d'exécution et en simplicité d'utilisation.

Mes dotfiles sont disponibles [ici](https://github.com/anhgelus/dotfiles).

### i3-wm

J'ai décidé d'utiliser `i3-wm` comme window manager car il s'agissait du tiling wm le plus populaire et car je souhaitais tester ce type de window manager.

Déjà pourquoi un tiling window manager ? Un tiling windows manager permet de naviguer à l'aide de raccourcie uniquement. Cette utilisation permet de gagner beaucoup en ergonomie et en rapidité d'exécution quand on y est habitué, comme ViM ET NeoVim d'ailleurs (que j'utilise aussi). J'ai donc décidé d'essayer d'utiliser ce type de wm pour me faire un avis dessus. Verdict : c'est génial !

Mes raccourcies sont ceux par défauts et la touche "mod" est la touche dite SUPER (le bouton windows du clavier).

Sinon, j'ai un gap entre les fenêtres et le bord pour rendre le tout plus beau.

### Polybar

Comme la bar d'i3 est moche, j'ai décidé de la changer par Polybar.

Polybar m'affiche à gauche les différents workspace que j'utilise ainsi que le nom de la fenêtre en cours. À droite, j'ai des informations sur l'espace restant à la racine, la disposition du clavier, l'utilisation de la RAM et du CPU, mon addresse IP local, la vitesse IO de mon ethernet et l'heure (au format H:i:s, par exemple : 16:25:48).

L'espacement entre Polybar et le bord de l'écran est bien sûr armonisé avec le gap des fenêtres.

## Compton

Pour améliorer l'aspect visuel d'i3, j'utilise Compton.

Ici, Compton rajoute du blur aux fenêtres non focus et le diminue quand la fenêtre a le focus. C'est d'ailleurs comme ça que je sais quel fenêtre possède le focus.

De plus, Compton rajoute une animation lors du déplacement des fenêtres.

### Workspace

J'utilise constamment 4 workspaces : 
- 1 : Workspace principal de travail sur l'écran principal
- 3 : Firefox sur l'écran secondaire
- 4 : Discord sur l'écran secondaire
- 10 : Spotify ou Amberol (lecteur de musique incroyable) sur l'écran secondaire

Quand j'ai besoin d'avoir un deuxième workspace sur l'écran principal, j'utilise le 2. Les autres (5, 6, 7, 8 et 9) peuvent être utilisés sur n'importe quel écran.

### Applications

Mon navigateur internet principal est [Firefox](https://www.mozilla.org/fr/firefox/new/) et j'utilise de temps en temps [Chromium](https://www.chromium.org/getting-involved/download-chromium/). Il se lance automatiquement en workspace 3 au démarrage de la session.

Mon application de chat est [Discord](https://www.discord.com/) qui se lance automatiquement en workspace 4.

Niveau musique, j'utilise [Spotify](https://www.spotify.com/) pour le streaming de musique et [Amberol](https://apps.gnome.org/fr/app/io.bassi.Amberol/) comme lecteur de musique hors ligne (faut bien que je profite de mes 50 albums !).

Pour développer, j'utilise essentiellement la suite JetBrains car il s'agit juste de la meilleure suite d'IDE du marché (meilleure autocomplétion) et qu'elle est gratuite pour moi puisque je suis [GitHub Student](https://education.github.com/students). Je peux aussi utiliser [Vim](https://www.vim.org/) pour l'édition rapide de fichier. Je compte bientôt installer [NeoVim](https://neovim.io/) car ce dernier est bien plus puissant que Vim.

Pour synchroniser les différents fichiers important entre mes différents appareils, j'utilise [Nextcloud](https://nextcloud.com/) self-host sur mon VPS. J'utilise aussi [KDE Connect](https://kdeconnect.kde.org/) pour lier mon téléphone à mon ordinateur.

Toujours dans cette optique de synchronisation, j'utilise aussi [Bitwarden](https://bitwarden.com/) pour avoir accès à tous mes identifiants, mot de passes, tokens et bien plus partout. Par contre, j'ai décidé de self-host mon serveur Bitwarden pour avoir une plein pouvoir sur ces données ! J'utilise donc [Vaultwarden](https://github.com/dani-garcia/vaultwarden) pour pouvoir le faire gratuitement.

## Utilisation principale

La principale utilisation de cet ordinateur est le développement et le sysadmin.

Grand fan de [Docker](https://www.docker.com/), je contenairise tout ce qui est possible.

J'utilise aussi grandement [Git](https://git-scm.com/) et [GitHub](https://github.com/) pour développer à plusieurs et pour partager mes projets.

## Conclusion

Cet environnement de travail me correspond parfaitement en 2023 mais ce ne sera pas forcément le cas pour vous !

Ne me copiez pas bêtement et essayez de comprendre pourquoi j'ai fait ces choix et insipez-vous en pour concevoir votre propre système.  ^^

Si vous avez des remarques ou des questions, hésitez pas à me contacter. Plus d'info [ici](https://blog.anhgelus.world/contact/).


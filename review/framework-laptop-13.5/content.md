Comme l'année prochaine, je serais en étude sup', je me suis donc mis à rechercher un laptop qui me conviendrait dans cette utilisation.
J'avais comme principaux critères les suivants :
- Ultrabook léger, assez puissant pour faire du développement et de la compilation de source code C/C++, et qui s'allume vite
- réparable, j'ai pas envie d'avoir à me faire chier s'il casse
- compatible Linux à 100% (car Linux > Windows pour moi)

Il y a quelque temps déjà, j'avais entendu parler d'un Ultrabook 100% réparable et compatible Linux.

Je me le suis donc pris et voici ma vidéo de retour après quelques jours/semaines d'utilisation.

## Si facile à monter, mais si dure à déballer

Je reçois donc mon laptop et je m'empresse de le déballer.

Premier constat, il est si bien emballer que mes ongles n'ont pas réussi à enlever le scotch qui servait à fermer la boite. C'est vraiment bien car on est sûr que le pc ne se fera pas déglinguer avec un tel emballage.

Ensuite, j'ouvre le paquet et je vois plusieurs boites en carton toute très bien agencé. Je sors la première et je la déballe. À l'intérieur, il y avait les extensions cards qu'on rajoute au laptop en fonction des ports qu'on a besoin. Il y avait aussi la présence des deux barrettes de RAM que j'avais commandé en même temps (et j'ai bien fait, vous allez comprendre pourquoi après).

Je sors ensuite la deuxième boite, aussi en carton, pour y découvrir un long câble d'alimentation, enfin, devrais-je dire un câble d'alimentation en 3 parties toutes remplaçables. Je le monte très facilement et je découvre qu'il doit facilement faire 1m50 voir 2m de long, ce qui est de plus en plus rare pour ce type de câble.

Après, je sors la dernière boite en carton, celle du laptop. Étrangement, aucun plastique ne le retient juste du carton encore une fois très bien agencé. Je sors donc le portable et je découvre le portable de 13.5''. Il est composé d'un acier robuste ce qui me rend confiant d'un point de vue durée de vie.

Je le retourne pour l'ouvrir et je découvre à quel point il est facile à ouvrir, quel plaisir. J'installe donc la RAM, je le referme et je mets 4 des 5 extensions cards que j'ai acheté : 
- 1 USB Type-C
- 2 USB Type-A
- 1 Port Ethernet

Très simple à installer, très solide, bref un système qui marche vraiment bien.

En bref, c'est un packaging qui est incroyable, car il n'utilise aucun matériaux non recyclable. De plus, le tout est vraiment très bien agencé et on sent la véritable volonté de le rendre durable.

## Premier boot et début des surprises

Après avoir donc créé une clef USB bootable de EndeavourOS, ma distribution Linux préférée, je l'insère ensuite dans l'ordinateur et je m'apprête à booter dessus sans aucun problème puisqu'il n'y a pas de disque à l'intérieur. Le bios en avait décidé autrement et je me retrouve avec une belle erreur me disant que je n'ai pas l'autorisation de le faire, wtf ? Je cherche ainsi rapidement sur internet et je découvre que l'erreur vient du fait que le secure boot est activé. Je cherche ensuite la touche pour y accéder (j'ai un peu galéré, voici la touche pour vous éviter cette galère : F2) et je le désactive. Finalement, je boot sur ma clef USB, je teste toutes les fonctionnalités et je suis surpris de la qualité de l'antenne Wi-Fi présente ainsi que du support du Bluetooth qui marche très bien.

## Le SSD arrive, et le véritable début des emmerdes

Mon Seagate Firecude 530 arrive quelques heures après le laptop. J'ouvre mon laptop et je place le SSD avec son énorme heatsink à l'intérieur, et j'essaye de le fermer. Il ne ferme pas. Le heatsink est beaucoup trop gros pour le PC. Je rouvre donc le laptop et sors le NVME.

Je me mets à dévisser les 4 vis qui tiennent le heatsink. La première vis s'enlève plutôt facilement, de même pour la dernière, par contre, impossible d'enlever les deux autres. J'essaye par la suite de les enlever, mais malheureusement, lors de mes différentes tentatives, j'ai défoncé leur pas alors que j'avais la bonne taille de tournevis... Bon, bah va falloir que j'aille me prendre une boite de tournevis de précision, et si ça ne fonctionne pas, un extracteur de vis.

Un jour passe et j'ai ma boite. Je sors un tournevis plat et j'arrive à dévisser les deux vis restantes. J'enlève donc le heatsink et je le replace dans mon laptop. Le laptop ne ferme toujours pas. Vous allez sûrement me demander pourquoi ? La réponse est simple, le reste du boitier empêche la fermeture. Or, on ne peut pas enlever le SSD de ce boitier. Je décide ainsi de commencer à arracher ce qui le bloque. Après 2/3 tentatives, j'arrive enfin à enlever ce qui dépassait et je remets mon NVME dans le portable. Il ferme et comme j'avais préalablement installé EndeavourOS avec Gnome vanilla, il boot parfaitement et tout marche bien.

N'achetez pas de NVME avec heatsink pour vos portables...

## Setup de l'ordinateur

Comme sur mon pc principal, j'ai déjà EndeavourOS d'installer, j'ai juste installé normalement l'ensemble des applications courantes que j'utilise.

Après, j'ai décidé de suivre 2 threads sur le forum de Framework. Le premier parlait d'optimisation de batterie et le deuxième de chose à faire après avoir installé EndeavourOS. Pour le premier, je n'ai eu qu'une seule chose à faire : rajouter `nvme.noacpi=1` dans les paramètres Grub. De plus, j'ai activé un paramètre pour l'accélération GPU dans Firefox (dans le `about:config`). L'ensemble des autres conseils étaient soit déjà appliqués par Gnome, soit une alternative était utilisée par Gnome. Ainsi, je n'ai dû éditer qu'un seul fichier pour avoir une durée sur batterie sur Linux environ égal à celle sur Windows. Ensuite, dans le deuxième thread, il recommandait d'installer des packets pour faire fonctionner le lecteur d'empreinte digitale ainsi que rajoutait plus de fonctionnalité au touchpad. J'ai installé les deux et je n'ai eu aucun problème avec.

Donc, setuper un framework avec Gnome, c'est simple et parfait pour la batterie (présence de Wayland à la place de Xorg, bonne gestion de la batterie par défaut).

## Let's rice!

Comme de base, je suis un utilisateur de tiling window manager (surtout i3wm enfaites), je n'ai pas pu m'empêcher de customiser mon gnome.

Pour ce faire, j'ai d'abord installé l'extension pour Firefox qui permet d'installer simplement des extensions via extensions.gnome.org, sauf qu'il manquait un packet pour cela marche. Je mets 15 minutes à trouver le packet (d'ailleurs, j'ai oublié son nom) et je l'installe. Ensuite, j'installe un petit lot d'extension pour rendre Gnome plus beau, voici la liste complète des extensions que je recommande :
- `Blur my Shell` - Rajoute du blur partout
- `Extension List` - Rajoute une icône permettant de paramétrer rapidement les extensions dans la top bar
- `Just Perfection` - Permet de customiser certain comportement par défaut du shell
- `OpenWeather` - Rajoute la météo dans la top bar
- `Quick Settings Tweaker` - Modifie beaucoup de chose naturellement présente dans la top bar pour la rendre plus ergonomique
- `Tiling Assistant` - Rajoute une meilleure gestion de la taille des applications
- `User Themes` - Permet la modification du thème du shell (je ne l'utilise pas, car Adwaita est très bien)
- `Vitals` - Rajoute des informations à propos du laptop dans la top bar (usage de la RAM, du CPU, d'internet, etc.)
- `Bluetooth Quick Connect` - Rajoute un moyen de se connecter rapidement à un appareil Bluetooth depuis le menu des paramètres rapides (inutile avec Gnome 44) 

Après, je me suis mis à chercher un fond d'écran, et oh boy, je savais que j'étais chiant en terme de fond d'écran, mais j'ai bien mis 2h à trouver ce que je voulais. Et le pire dans l'histoire, c'est que comme chez Framework, ils ont décidé de mettre un très bon écran en 3:2 avec une hauteur de 1504p, il devient donc très complexe de trouver un fond d'écran qui marche pour cette résolution ! Au final, j'ai trouvé un fond d'écran en FHD que j'ai upscale en UHD (aka 4k).

Mais bon, comme d'habitude, rice Gnome c'est simple et plaisant.
PS : n'installer ni `Dash To Dock` ni `Dash To Panel` sinon vous allez rendre l'UX de Gnome beaucoup moins intéressante et plaisante !

## Benchmarks

Mais en termes de perf, qu'est-ce que ça vaut ?

Pour rappel, j'ai l'édition DIY du Framework 12e gen avec un 1240p et 16 go de RAM.
Pour être franc, je n'ai pas fait de benchmark abstrait, je n'ai "que fait" de l'utilisation réelle.


Commençons avec la batterie.

Avec mon setup actuel, en économie d'énergie, je tiens facile 7h en l'utilisant pour de la bureautique ou du développement sans compilation vénère.

En équilibré, on tourne plus autour de 6h sans jouer et autour de 3h en jouant à Minecraft avec mon [modpack](https://modrinth.com/modpack/little-improved-vanilla). Le 60 fps était à peu près tenu même si le 1% low est autour de 50 fps pour une survie classique (il ne faut pas oublier que j'avais sodium + iris + distant horizon à 32 chunks de render distance, le tout en 1504p).

Sinon, pour le mode performance, je n'en ai aucune idée, car je n'ai encore jamais eu l'occasion de l'utiliser.

Sinon, quand on ferme l'écran, on peut économiser beaucoup de batterie : on perd environ 1% pour 2h avec aucune app de lancer, 1% en 30 min avec Firefox de lancer et quelques tabs, et plusieurs % par heure avec quelques applications de lancer.

L'ordinateur est donc parfaitement utilisable pour une journée complète de cours, surtout si on a une batterie externe.


Continuons avec la vitesse en général.

Je n'ai senti aucun ralentissement concernant l'OS, que ce soit sur batterie ou sur secteur, même quand je compilais `wine` et quelques packets `AUR`.

Goland (mon IDE pour le magnifique langage de programmation qu'est Golang) n'a pour l'instant jamais lagué.

Pour conclure, pour de la bureautique et des jeux légers, il n'y aura aucun problèmes de batterie et de performance.

## Les bugs

Wayland c'est plutôt récent, et de nombreuses apps ne le supporte pas encore bien.

Premièrement, impossible de partager son écran avec Discord (snap et flatpak) puisque ce dernier supporte que Xorg...

Autre problème avec OBS : il ne supporte pas le système de workspace de gnome, ce qui est très embêtant quand on souhaite montrer notre workflow... Et vous allez sûrement me dire d'utiliser l'application de screenshot de Gnome... oui, elle marche très bien, mais l'enregistrement lag dès que je change de workspace, donc aussi inutilisable dans cette utilisation. Ce qui aurait pu être pas mal, ce serait de pouvoir choisir la résolution à laquelle on souhaite enregistrer, car le 1240p ne supporte pas du tout du 1504p en encodage...

## Conclusion

Pour conclure, le laptop DIY 12e gen de Framework est une grosse surprise.

Premièrement sa philosophie est géniale, il offre de bonnes performances et tient très bien sur batterie avec EndeavourOS et Gnome.

Par contre, son prix est un poil trop élevés (300€ trop chères selon moi).

Je ne peux donc que vous le conseillez si vous souhaitez obtenir un ultrabook durable et 100% réparable.

Site web de framework : https://frame.work/fr/fr

# Tutos GameMaker Studio 2

*par flashjaysan*

## Ressources essentielles de GameMaker Studio 2

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous présenter les trois ressources essentielles de ce moteur.

Après avoir créé un nouveau projet dans GameMaker, vous pouvez immédiatement tester votre jeu en cliquant sur le bouton `Run` situé sous les menus ou plus simplement en pressant la touche `F5` de votre clavier.
Sur la droite de l'éditeur, le panneau `Resources` contient différentes sections.
Ce panneau est le point central de tout projet.
Toutes les ressources utilisées dans votre jeu seront accessibles depuis ce panneau.

Une room est la première ressource essentielle à un jeu dans GameMaker.
C'est simplement un écran de jeu comme l'écran de titre, d'options ou plus généralement un niveau de jeu.
Dans le panneau `Resources`, déployez la section `Rooms`. Vous pouvez constater que pour tout nouveau projet, GameMaker vous fournit par défaut une ressource de type Room et portant le nom `room0`.
Pour créer une room, faites un clic droit sur la section `Rooms` du panneau `Resources` et choisissez l'option `Create Room` (ou utilisez le raccourci `ALT+R`).
Attention ! GameMaker exécute toujours la première room de la liste au démarrage du jeu.
Si vous avez créé une nouvelle room assurez vous que la `room0` se trouve en premier dans la liste.
Si ce n'est pas le cas, faites-la glisser au dessus des autres dans le panneau `Resources`.
Double cliquez sur la ressource `room0` pour l'ouvrir dans l'éditeur.
Sur la gauche, vous voyez apparaître les propriétés de la room que vous pouvez éditer à votre convenance.
Si vous avez exécuté votre projet, vous avez pu constater que la room est vide.

Un objet est la deuxième ressource essentielle à un jeu dans GameMaker.
C'est simplement un élément interactif et autonome du jeu.
Chaque objet peut déclencher certaines actions lorsque certains événements se produisent.
Retenez bien ce terme d'**événement**.
Tout le fonctionnement de GameMaker tourne autour de ce principe.
C'est grâce aux différents événements et aux actions qui leur sont associées que vous pourrez vraiment concevoir votre jeu.
Par défaut, la section `Objects` du panneau `Resources` est vide.
Pour créer un objet, faites un clic droit sur la section `Objects` du panneau `Resources` et choisissez l'option `Create Object` (ou utilisez le raccourci `ALT+O`).
Un objet nouvellement créé s'affiche alors dans l'éditeur.
Cliquez sur le bouton `Add Event` de la fenêtre `Events` liée à cet objet.
Vous pouvez constater que GameMaker fournit de très nombreux événements pour contrôler finement votre jeu.
Sélectionnez l'événement `Key Pressed -> Others -> Escape`.
Cet événement se déclenche lorsque le joueur appui sur la touche `échap` de son clavier.
Une fenêtre de code s'affiche.
Saisissez simplement le code suivant : `game_end();`.
Attention ! Vous devez le saisir exactement comme je l'ai fait. Une petite faute de frappe entraînera une erreur.
Si vous souhaitez consulter la documentation sur cette fonction, cliquez avec le bouton du milieu de la souris sur la fonction.
La fonction `game_end` fournie par GameMaker force la fermeture du jeu.
Autrement dit, si le joueur appuie sur la touche `échap` de son clavier, le jeu se termine.
Mais pour que cela fonctionne correctement, l'objet doit être placé dans une room.
Si ce n'est pas déjà fait, double cliquez sur la ressource `room0` pour l'ouvrir dans l'éditeur puis faites glisser l'objet depuis le panneau `Resources` vers la room.
Si vous exécutez le projet, vous ne verrez toujours rien s'afficher à l'écran.
En revanche, si vous appuyez sur la touche `échap`, votre jeu se ferme automatiquement.
Pour qu'un objet affiche quelque chose, vous devez lui attribuer une ressource graphique appelée sprite.

Un sprite est la troisième ressource essentielle à un jeu dans GameMaker.
C'est simplement un élément graphique du jeu.
Pour créer un sprite, faites un clic droit sur la section `Sprites` du panneau `Resources` et choisissez l'option `Create Sprite` (ou utilisez le raccourci `ALT+S`).
Un sprite nouvellement créé s'affiche alors dans l'éditeur.
Il est constitué par défaut d'une seule image vide de 64 pixels de large sur 64 pixels de haut.
Pour éditer l'image, cliquez sur le bouton `Edit Image`.
Comme vous pouvez le constater, GameMaker fournit un éditeur d'image assez complet pour créer vos sprites directement dans l'éditeur.
Bien entendu vous pouvez également importer des images provenant de sources externes au moteur.
Pour l'exemple, je vais simplement cliquer sur l'outil pot de peinture, choisir une couleur parmi celles proposées et remplir l'image avec cette couleur en cliquant sur son canevas au centre de l'éditeur.
Une fois votre image créée, fermez l'éditeur puis attribuez le sprite à votre objet.
Pour cela double cliquez sur l'objet dans le panneau `Resources` pour l'afficher dans l'éditeur.
Cliquez sur le bouton `No Sprite` et choisissez le sprite dans la liste.
Si vous ouvrez la `room0`, vous voyez alors apparaître le sprite là où vous aviez déposé l'objet.
Exécutez le projet et vous verrez également s'afficher le sprite dans la fenêtre.

Voilà ! C'est tout pour ce rapide tutoriel d'introduction.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Déplacer un objet avec le clavier

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous présenter différentes approches pour gérer le mouvement d'un objet en continu avec les touches du  clavier.

Tout d'abord voici un petit rappel sur le système de coordonnées dans GameMaker.
Double cliquez sur la ressource `room0`.
Lorsque vous déplacez votre souris, vous pouvez voir les coordonnées du pointeur relativement à l'origine de la room, en bas à gauche de l'éditeur.
Vous pouvez constater que :
- l'axe horizontal (le premier nombre) augmente vers la droite,
- l'axe vertical (le second nombre) augmente vers le bas,
- l'origine du système de coordonnées se trouve dans le coin supérieur gauche de la room.
Fermez l'éditeur de room et ouvrez votre objet dans l'éditeur.

Cliquez sur le bouton `Add Event` de votre objet pour afficher la liste des événements disponibles.
Les évènements `Key Pressed` et `Key Up` se déclenchent une seule fois à l'instant où le joueur appuie sur une touche du clavier ou la relâche.
Si vous utilisez ces événements, le joueur devra sans arrêt appuyer puis relâcher la touche du clavier pour déplacer l'objet.
Ce n'est donc pas adapté à un déplacement continu d'un objet.
Vous pouvez toutefois utiliser ces événements pour un déplacement d'un objet case par case.
L'événement `Key Down` en revanche se déclenche à chaque rafraichissement d'écran, ou **step**, tant que le joueur appuie sur une touche du clavier.
Vous pouvez donc utiliser cet événement pour déplacer votre objet en continu.

Choisissez l'événement `Key Down -> right`.
Dans l'éditeur de code, saisissez le code suivant : `x += 5;`
Ce code, traduit en français veut simplement dire : Fais l'addition de la valeur de droite et de la valeur de gauche et stocke le résultat dans la valeur de gauche.
Vous avez peut être déjà vu une autre notation équivalente dans d'autres langages de programmation : `x = x + 5;`
Mais cette notation, en plus de répéter le terme `x` peut paraître étrange à un débutant habitué aux égalités mathématiques.
En utilisant directement l'opérateur `+=`, on indique de manière explicite que l'on veut ajouter la partie de droite à la partie de gauche.
Autrement dit, on ajoute la valeur `5` à la propriété `x` de l'objet.
La propriété `x`, fournie par GameMaker pour tous les objets, correspond à la position horizontale de l'objet dans la room.
Si on lui ajoute `5`, cela veut dire qu'on déplace l'objet de 5 pixels vers la droite.
Si ce code s'exécute à chaque step où le joueur appuie sur la touche droite du clavier, cela signifie que l'objet va se déplacer de 5 pixels vers la droite 60 fois par seconde.
Pour tester ce fonctionnement, placez votre objet dans la ressource `room0` puis exécutez votre jeu.
Si vous appuyez sur la touche droite du clavier, l'objet va se déplacer rapidement vers la droite et même sortir de l'écran.
Nous verrons comment corriger ce problème dans une autre vidéo.

Maintenant que vous avez compris le principe, je pense que vous êtes capable de gérer le déplacement vers la gauche avec la touche gauche et en utilisant l'opérateur `-=` qui soustrait la valeur de droite à la valeur de gauche.
En revanche, pour les touches haut et bas, souvenez-vous que c'est la propriété `y` qu'il faudra modifier.
Pour vous entraîner et voir si vous avez bien compris, je vous laisse le soin de gérer les trois autres touches.
Si jamais vous êtes toujours bloqué, la description de cette vidéo donne les instructions à placer dans chaque événement.

Une autre approche, plus polyvalente, est d'utiliser l'événement `Step`.
Cet événement se déclenche à chaque step du jeu (d'où son nom) soit 60 fois par secondes.
Dans ce cas, vous devez contrôler manuellement si une touche du clavier est enfoncée ou non en utilisant les fonctions fournies par GameMaker.
Supprimez les événements précédents de l'objet et ajoutez l'événement `Step` à l'objet.
A l'instar des évènements `Key Pressed` et `Key Up`, les fonctions `keyboard_check_pressed` et `keyboard_check_released` fournies par GameMaker renvoient une valeur booléenne indiquant si une touche spécifique vient d'être enfoncée ou relâchée.
Ces fonctions renvoient donc une valeur vraie uniquement lorsque le joueur vient d'enfoncer ou de relâcher la touche.
Ces fonctions ne sont donc pas adaptées à notre besoin mais elles peuvent être idéales pour déclencher un saut ou un tir.
En revanche, la fonction `keyboard_check` fournie par GameMaker renvoie une valeur booléenne indiquant si une touche en enfoncée au moment de son appel.
Elle permet donc de vérifier l'appui sur une touche du clavier en continu.
Dans le cas présent, c'est la fonction à utiliser.
Saisissez le code suivant :

```js
if keyboard_check(vk_right)
{
    x += 5;
}
```

Comme tout à l'heure, on retrouve l'instruction `x += 5;` mais cette fois dans un bloc qui s'exécute uniquement si une condition est vraie.
Cette condition est vraie lorsque la touche associée à la constante prédéfinie `vk_right` est enfoncée.
Et cette touche, c'est la touche `droite` du clavier.
Si vous avez compris le principe, je vous laisse à nouveau le soin de faire la gestion du déplacement pour les touches `gauche`, `haut` et `bas`.
Utilisez simplement les constantes prédéfinies `vk_left`, `vk_up` et `vk_down` pour faire référence aux touches du clavier.
Utiliser l'événement `Step` vous permet de rassembler toutes la gestion des contrôles dans un seul événement et donc de pouvoir gérer les situations où plusieurs touches sont appuyées en même temps.
Nous verrons dans une future vidéo pourquoi c'est important.
Attention ! Pour gérer les chiffres et les lettres du clavier, au lieu d'utiliser des constantes prédéfinies, vous devez appeler la fonction ord fournie par GameMaker en passant le chiffre ou la lettre entre guillemets.

Voilà ! C'est tout pour ce rapide tutoriel d'introduction.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Limiter la position d'un objet dans une room (première partie)

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous expliquer comment limiter la position d'un objet dans une room.

Pour ne pas partir de zéro, je vais me baser sur ce que je vous ai présenté dans une précédente vidéo pour déplacer un objet avec les touches du clavier.
Je vous invite donc à consulter cette vidéo si vous ne comprenez pas bien le code que je vais utiliser comme point de départ.

Pour faire bouger votre objet, utilisez le code suivant dans l'événement `Step` (si vous préférez, vous pouvez copier le code depuis la description de cette vidéo) :

```js
if keyboard_check(vk_right)
{
    x += 5;
}
if keyboard_check(vk_left)
{
    x -= 5;
}
if keyboard_check(vk_down)
{
    y += 5;
}
if keyboard_check(vk_up)
{
    y -= 5;
}
```

Dans ma vidéo précédente, vous aviez pu constater que l'objet se déplaçait en continu lors de l'appui des touches du clavier mais pouvait malheureusement sortir des limites de la room.
Nous allons donc remédier à cela dans cette vidéo.

Pour bien comprendre le problème, examinons à nouveau le système de coordonnées d'une room.
Dans la section `Rooms` du panneau `Resources`, double cliquez sur la ressource `room0`.
Si votre objet n'est pas déjà dans la room, faites-le glisser dans la room depuis le panneau `Resources`.
Faites un double clic sur votre objet dans la room.
Un nouveau panneau s'affiche avec diverses propriétés de l'objet.
Les propriétés `x` et `y` définissent la position de l'objet dans la room.
Déplacez votre objet dans la room avec le `bouton gauche` de la souris et vous verrez ces propriétés changer de valeur en temps réel.
Positionnez votre objet dans le coin supérieur gauche de la room.
Lorsque les propriétés `x` et `y` de l'objet valent `0`, l'objet est positionné précisément dans le coin supérieur gauche de la room.
Vous pouvez donc en déduire que pour que l'objet reste dans la room, les propriétés `x` et `y` doivent être positives ou nulles.
Dans l'événement `Step` de votre objet, saisissez le code suivant, à la suite du code existant :

```js
if x < 0
{
    x = 0;
}
```

Exécutez votre jeu pour constater que l'objet ne peux plus sortir de la room par la gauche.
Pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet afin d'empêcher l'objet de sortir de la room par le haut.

Vous avez traité le bord supérieur et le bord gauche de la room mais votre objet peut encore sortir de la room par le bord inférieur et le bord droit.
Retournez dans l'éditeur de room et positionnez votre pointeur de souris sur le coin inférieur droit de la room.
Faites bien attention aux coordonnées affichées en bas à gauche de la fenêtre de l'éditeur.
Maintenant, jetez un oeil aux propriétés de votre room dans le panneau `Room Editor` à gauche de l'écran.
Dans la section `Properties`, en bas du panneau, vous trouvez la sous-section `Room Settings` qui contient les dimensions de la room.
Ce sont les propriétés `Width` (largeur) et `Height` (hauteur).
Copiez ces valeurs dans les propriétés `x` et `y` dans le panneau des propriétés de votre objet.
Si vous avez fermé ce panneau, faites simplement un double clic sur votre objet dans la room.
Lorsque vous donnez aux propriétés `x` et `y` de votre objet les valeurs associées aux dimensions de la room, votre objet se positionne dans le coin inférieur droit de la room.
Vous pouvez donc en déduire que pour que l'objet ne sorte pas des limites droites et basses de la room, les propriété `x` et `y` de l'objet ne doivent pas dépasser les dimensions de la room.
Dans l'événement `Step` de votre objet, saisissez le code suivant, à la suite du code existant :

```js
if x > 1024
{
    x = 1024;
}
```

Si votre room a une largeur différente, remplacez la valeur `1024` par la largeur de votre room.
Plutôt que d'utiliser une valeur numérique que vous devrez modifier à chaque fois que vous changerez les dimensions de votre room, utilisez plutôt les deux variables `room_width` et `room_height` fournies par GameMaker.
Modifiez votre code précédent comme ceci :

```js
if x > room_width
{
    x = room_width;
}
```

Notez que le premier pixel en haut à gauche de la room est à la coordonnée `(0,0)`. Le dernierpixel en bas à droite de la room est donc à la coordonnée `(room_width - 1, room_height - 1)`.
Vous devriez donc soutraire `1` au variables `room_width` et `room_height` à chaque fois.
Pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet afin d'empêcher l'objet de sortir de la room par le bas.
Pensez à utiliser la variable prédéfinie `room_height`.

Exécutez votre jeu et déplacez votre objet sur les différents bords de la room.
Vous constatez qu'il y a un problème pour le bord droit et le bord inférieur.
Votre objet sort encore des limites de la room.
Le problème est complexe et nous l'aborderons plus en détail dans une prochaine vidéo.
Pour le moment, nous allons juste vérifier que le code que vous avez utilisé limite bel et bien la position de l'objet aux limites de la room.

Faites un double clic sur le sprite attribué à votre objet dans le panneau `Resources`.
L'éditeur de sprite apparaît.
Dans la partie centrale, vous pouvez voir l'image de votre sprite avec une petite croix dans son coin supérieur gauche.
Cette croix indique le point d'origine du sprite.
Ce point d'origine se trouve toujours par défaut dans le coin supérieur gauche de l'image.
Au dessus de l'image, un menu déroulant vous permet de positionner ce point d'origine sur des points prédéfinis de l'image.
Sélectionnez l'option `Middle Center`.
Le point d'origine se place alors au centre de l'image.
Exécutez à nouveau votre jeu et vous pourrez constater que le centre du sprite de l'objet ne peut pas sortir des limites de la room.
Vous avez donc bien un fonctionnement correct de votre code.

Pour terminer, GameMaker fournit la fonction `clamp` qui permet de limiter une valeur dans un intervalle donné.
Plutôt que d'utiliser le code précédent, voici une façon beaucoup plus concise de faire la même chose :

```js
x = clamp(x, 0, room_width - 1);
```

Cette fonction prend la première valeur passée en paramètre, la limite entre les deux autres paramètres et renvoie cette nouvelle valeur.
Notez que la fonction ne modifie pas la valeur directement c'est pourquoi on doit récupérer la valeur renvoyée par la fonction dans la propriété `x`.
Une dernière fois, pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet.
Utilisez la variable prédéfinie `room_height`.

Voilà ! C'est tout pour cette fois.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Limiter la position d'un objet dans une room (deuxième partie)

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais continuer à vous expliquer comment limiter un objet dans une room.

Pour ne pas partir de zéro, je vais me baser sur ce que je vous ai présenté dans la précédente vidéo pour déplacer un objet avec les touches du clavier et limiter sa position dans la room.
Je vous invite donc à consulter cette vidéo si vous ne comprenez pas bien le code que je vais utiliser comme point de départ.

Utilisez le code suivant dans l'événement `Step` (si vous préférez, vous pouvez copier le code depuis la description de cette vidéo) :

```js
if keyboard_check(vk_right)
{
    x += 5;
}
if keyboard_check(vk_left)
{
    x -= 5;
}
if keyboard_check(vk_down)
{
    y += 5;
}
if keyboard_check(vk_up)
{
    y -= 5;
}
x = clamp(x, 0, room_width - 1);
y = clamp(y, 0, room_height - 1);
```

Dans ma vidéo précédente, vous aviez pu constater que le sprite de l'objet dépassait des limites de la room.
Nous allons donc remédier à cela dans cette vidéo.

Pour gérer correctement le placement du sprite de l'objet dans les limites de la room, vous devez prendre en compte la position du point d'origine du sprite ainsi que ses dimensions.
Faites un double clic sur le sprite attribué à votre objet dans le panneau `Resources`.
L'éditeur de sprite apparaît.
Cliquez n'importe où sur l'image pour positionner le point d'origine sous le curseur de la souris.
A côté du menu déroulant au dessus de l'image, vous pouvez voir les coordonnées du point d'origine par rapport au coin supérieur gauche de l'image.
Ce point d'origine est très important car c'est lui qui détermine le point d'ancrage du sprite par rapport à la position de l'objet dans la room.
Imaginez simplement que vous plantez une punaise sur l'image au niveau de ce point d'origine et que la pointe de cette punaise définit la position de l'image quand vous placez un objet avec ce sprite dans la room.
Comme le point d'origine se trouvait dans le coin supérieur gauche, lorsque vous déplaciez l'objet sur le bord droit ou le bas de la room, le sprite se positionnait sur son point d'origine et toute la partie droite et basse de l'image sortait du cadre.
Si ce n'est pas déjà fait, cliquez sur le menu déroulant et sélectionnez l'option `Middle Center`.
Le point d'origine se place au centre de l'image.
Exécutez votre projet et déplacez l'objet avec les touches du clavier jusqu'aux différents bords de la room.
Comme le point d'origine est au centre de l'image, une moitié de l'image sort de la room.

Pour que le sprite de l'objet reste entièrement dans la room, vous devez prendre en compte la moitié des dimensions du sprite.
Les variables non modifiables `sprite_width` et `sprite_height` fournies par GameMaker contiennent respectivement la largeur et la hauteur du sprite attribué à un objet.

Dans l'événement `Step` de votre objet, supprimez les deux dernières lignes de votre code et saisissez le code suivant :

```js
x = clamp(x, sprite_width / 2, room_width - 1 - sprite_width / 2);
```

Pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet.
Pensez à utiliser la variable `sprite_height`.
Exécutez votre jeu pour vérifier que le sprite de votre objet reste bien entièrement dans les limites de la room.

Maintenant que vous savez comment faire pour un point d'origine situé au centre du sprite, je vais vous présenter la méthode pour gérer n'importe quelle position de ce point d'originedans le sprite.
Faites un double clic sur le sprite attribué à votre objet dans le panneau `Resources`.
L'éditeur de sprite apparaît.
Cliquez n'importe où sur l'image pour positionner le point d'origine à un endroit quelconque.
A côté du menu déroulant au dessus de l'image, vous pouvez voir les coordonnées du point d'origine.
Vous pourriez donc utiliser directement ces valeurs pour gérer manuellement le décalage dans votre code.
Mais encore une fois, nous allons utiliser les fonctionnalités fournies par GameMaker.
Les variables non modifiables `sprite_xoffset` et `sprite_yoffset` contiennent le décalage (ou *offset*) du point d'origine par rapport au coin supérieur gauche du sprite.
Pour obtenir la position du bord gauche du sprite dans la room vous pouvez donc soustraire à la propriété `x` de l'objet, le décalage horizontal du point d'origine du sprite.

```js
bord_gauche_du_sprite = x - sprite_xoffset
```

Le sprite de l'objet sort à gauche de la room lorsque la position horizontale de son bord gauche devient négatif :

```js
bord_gauche_du_sprite < 0
```

Soit :

```js
x - sprite_xoffset < 0
```

Si on `sprite_xoffset` des deux côté de cette expression, on obtient :

```js
x < sprite_xoffset
```

Vous pouvez donc modifier la fonction `clamp` pour la propriété `x` de l'objet comme ceci :

```js
x = clamp(x, sprite_xoffset, room_width - 1);
```

Exécutez votre projet et vérifiez que le sprite ne peut plus sortir par la gauche de la room.
Pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet.
Pensez à utiliser la variable `sprite_yoffset`.

Occupons nous maintenant de la partie droite de la room.
Pour obtenir la position du bord droit du sprite, c'est un peu plus compliqué. Vous devez ajouter à la propriété `x` de l'objet, la largeur du sprite moins le décalage horizontal du point d'origine du sprite.

```js
bord_droit_du_sprite = x + sprite_width - sprite_xoffset
```

Le sprite de l'objet sort à droite de la room lorsque la position de son bord droit dépasse la largeur de la room :

```js
bord_droit_du_sprite > room_width - 1
```

Soit :

```js
x + sprite_width - sprite_xoffset > room_width - 1
```

Si on soustrait `sprite_width - sprite_xoffset` des deux côté de cette expression, on obtient :

```js
x < room_width - 1 - sprite_width + sprite_xoffset
```

Vous pouvez donc à nouveau modifier la fonction `clamp` pour la propriété `x` de l'objet comme ceci :

```js
x = clamp(x, sprite_xoffset, room_width - 1 - sprite_width + sprite_xoffset);
```

Exécutez votre projet et vérifiez que le sprite ne peut plus sortir par la droite de la room.
Pour vous entraîner et vérifier que vous avez bien compris, je vous laisse le soin de faire de même pour la propriété `y` de l'objet.
Pensez à utiliser la variable `sprite_yoffset`.

Et voilà ! Votre objet ne sort plus de la room quelle que soit la position de son point d'origine.
J'espère que vous n'aurez pas trouvé ça trop compliqué.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Améliorer le mouvement d'un objet

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous présenter …………………………....



Voilà ! C'est tout pour ce rapide tutoriel d'introduction.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Bases d'un plateformer partie 1

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous présenter …………………………....

 au pixel près dans GameMaker Studio 2.
Tout d'abord, voyons la gravité.
Tous les objets dans GameMaker Studio 2 ont une variable prédéfinie appelée gravity.

Voilà ! C'est tout pour ce rapide tutoriel d'introduction.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

## Template

Salut c'est Jaysan !
Bienvenue dans cette série de vidéos sur GameMaker Studio 2.
Dans cette vidéo, je vais vous présenter …………………………....

...................................

Voilà ! C'est tout pour ce rapide tutoriel d'introduction.
Je vous donne rendez-vous dans une prochaine vidéo sur GameMaker Studio 2.
Allez salut !

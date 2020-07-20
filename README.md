# COOKIE
This code allows you to trigger 1st 2nd and third party cookies from GTM based on user's decision on first visit.

# DANS LE FICHIER HEAD.HTML

1°) <!-- Optimize Page Hiding Snippet -->
* Modifier le code UA
Modifier le code GTM 'GTM-{your-code}'(attention ceci n'est pas le code figurant dans Google Tag Manager mais Optimize)

2°) <!-- Analytics-Optimize Snippet -->
* Modifier le code Optimize (UA-70111603-1) par celui figurant dans le compte Optimize correspondant
Modifier le code GTM-{your-code}'(attention ceci n'est pas le code figurant dans Google Tag Manager mais Optimize)

3°)SI ce code existe : Suppression de <!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-113887609-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'UA-{your-code}-1');
</script>
<!-- END OF Global site tag (gtag.js) - Google Analytics —>
> Car ce script empêche le fonctionnement de GTM, il faut l’enlever.

4°) <!-- Tarteaucitron Snippet -->
Avant cette étape, il faut définir des variables dans GTM. Exemple : si on veut mettre adroll, il faut mettre aussi adroll dans GTM en tant que variable.

Ajouter/Supprimer les cookies nécessaires/non nécessaires dans :
   * -const cookieRef =

* Ajouter/Supprimer les cookies nécessaires/non nécessaires dans :
    * dataLayer.push
Pour que cela fonctionne, il faut que les cookies soient dans le même ordre.

5°) <!-- Google Tag Manager -->
* Mettre le bon numéro GTM, pour le trouver aller dans Google Tag Manager et cliquer sur l'ID :
    *     





# DANS LE FICHIER FOOTER.HTML

1) <!-- Host Tarte au citron -->
Remplacer l'URL avec l'URL correspondant : <script type="text/javascript" src="https://s3-eu-west-3.amazonaws.com/gestion-de-cookies/RDPM/tarteaucitron/tarteaucitron.js"></script>

2) <!-- Cookie Push -->  
Mettre les cookies dans ce format (dans cet exemple changer nomdelavariable par la variable correspondante) :
//adroll
  (tarteaucitron.job = tarteaucitron.job || []).push('adroll');

3)  //ANALYTICS
Remplacer le code UA-70111603-1 par celui correspondant.

4) <!-- Google Tag Manager (noscript) -->
Remplacer l'URL avec le GTM id correspondant (aller dans Google Tag Manager, cliquer sur l'identifiant GTM en haut à droite à côté de Preview :  
https://www.googletagmanager.com/ns.html?id=GTM-{yourcode}

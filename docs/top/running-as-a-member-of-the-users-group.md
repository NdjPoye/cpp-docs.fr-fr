---
redirect_url: /cpp/security/running-as-a-member-of-the-users-group
caps.handback.revision: 17
---
# Ex&#233;cution en tant que membre du groupe Utilisateurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment la configuration de comptes d'utilisateurs Windows en tant que membres du Groupe Utilisateurs \(par opposition au Groupe Administrateurs\) améliore la sécurité et réduit le risque d'être infecté par un code malveillant.  
  
## Risques de Sécurité  
 L'exécution en tant qu'administrateur rend votre système vulnérable à plusieurs sortes d'attaque de sécurité, comme le « Cheval de Troie » ou le « dépassement de mémoire tampon ». Une simple visite d'un site Internet en tant qu'administrateur peut endommager le système, si un code malveillant téléchargé depuis un site Internet attaque votre ordinateur.  S'il y parvient, il hérite de vos autorisations d'administrateur et peut alors perpétrer des actions telles que supprimer tous vos fichiers, reformater votre disque dur, et créer de nouveaux comptes utilisateurs avec accès d'administration.  
  
## Groupes Utilisateurs non Administrateurs  
 Les comptes utilisateurs Windows normalement utilisés par les développeurs doivent être ajoutés aux groupes Utilisateurs ou Utilisateurs avec pouvoir.  Les développeurs doivent également être ajoutés au groupe Débogage.  Être membre du groupe Utilisateurs permet d'effectuer des tâches habituelles, notamment exécuter les programmes et visiter des sites Internet sans exposer son ordinateur à des risques inutiles.  En tant que membre du groupe Utilisateurs avec pouvoir, il est également possible d'effectuer des tâches telles que l'installation d'application, d'imprimante, et la plupart des opérations du panneau de configuration.  Si vous devez exécuter des tâches d'administration telles que mettre à niveau le système d'exploitation ou configurer les paramètres du système, vous devez vous connecter à un compte d'administrateur juste le temps d'exécuter la tâche d'administration.  La commande Windows **runas** peut également être utilisée pour lancer des applications spécifiques avec un accès d'administration.  
  
## Exposition des clients aux risques de sécurité  
 Il est particulièrement important que les développeurs ne fassent pas partie du groupe Administrateurs car, outre la protection des ordinateurs de développement, cela évite aux développeurs d'écrire par inadvertance du code qui exigerait que les clients fassent partie du Groupe Administrateurs pour pouvoir exécuter les applications que vous développez.  Si un code qui requiert l'accès administrateur est introduit au cours du développement, il échouera pendant l'exécution et déclenchera une alerte indiquant que les clients doivent désormais exécuter votre application en tant qu'Administrateurs.  
  
## Code qui requiert des privilèges Administrateurs  
 Certains codes requièrent un accès Administrateur pour s'exécuter.  Il faut dans la mesure du possible trouver des alternatives à ce code.  Les exemples qui suivent sont des opérations de code qui requièrent l'accès Administrateur :  
  
-   Écriture dans les zones protégées du système de fichiers, telles que les répertoires Windows ou Program Files  
  
-   Écriture dans les zones protégées du Registre, tel que HKEY\_LOCAL\_MACHINE  
  
-   Installation d'assemblys dans le GAC \(Global Assembly Cache\)  
  
 En général, ces actions sont réservées aux programmes d'installation des applications.  Elles permettent aux utilisateurs d'utiliser le statut d'administrateur seulement de façon temporaire.  
  
## Débogage  
 Vous pouvez déboguer n'importe quelle application lancée dans Visual Studio \(natif et non managé\) en tant que non administrateur en devenant membre du Groupe Débogage.  Cela permet notamment d'attacher au processus d'une application en cours d'exécution, à l'aide de la commande Attacher au processus.  Toutefois, il est nécessaire de faire partie du Groupe Administrateurs pour déboguer des applications natives ou managées lancées par un utilisateur différent.  
  
## Voir aussi  
 [Meilleures pratiques pour la sécurité](../top/security-best-practices-for-cpp.md)
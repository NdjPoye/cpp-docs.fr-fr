---
title: "Guide du portage&#160;: Scribble MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Guide du portage&#160;: Scribble MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique est la première d'une série de rubriques qui présentent le processus de mise à niveau de projets Visual C\+\+ créés dans des versions antérieures de Visual Studio vers [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  Ces rubriques abordent la mise à niveau en commençant par un exemple de projet très simple, avant de traiter des exemples de projets un peu plus complexes.  Dans cette rubrique, nous effectuerons la mise à niveau d'un projet spécifique, appelé Scribble MFC.  C'est un exemple qui nous permettra d'aborder les notions de base de la mise à niveau de projets C\+\+.  
  
 Chaque version de Visual Studio présente des incompatibilités susceptibles de compliquer la migration du code d'une version antérieure de Visual Studio vers une version plus récente.  Des modifications sont parfois à effectuer directement dans votre code et, dans ce cas, vous devez recompiler et mettre à jour le code. Des modifications peuvent également être nécessaires dans les fichiers projet.  Quand vous ouvrez un projet qui a été créé avec une version antérieure de Visual Studio, Visual Studio vous demande automatiquement s'il faut mettre à jour le projet ou la solution vers la dernière version.  En général, ces outils mettent à niveau les fichiers projet uniquement, sans modifier le code source.  
  
## Scribble MFC  
 Scribble MFC est un exemple bien connu qui a déjà été utilisé dans de nombreuses versions différentes de Visual C\+\+.  C'est une application de dessin simple qui illustre certaines fonctionnalités de base de MFC.  L'application est disponible dans différentes versions, y compris en code managé et en code natif.  Pour cet exemple, nous avons trouvé une ancienne version de Scribble en code natif de Visual Studio 2005 et l'avons ouverte dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)].  
  
 Avant de procéder à la mise à niveau, nous avons sauvegardé notre solution complète et tout son contenu.  Ensuite, nous avons dû choisir une méthode de mise à niveau.  Pour les projets et solutions plus complexes qui n'ont pas été mis à niveau récemment, prévoyez d'effectuer la mise à niveau d'une seule version de Visual Studio à la fois.  Vous pouvez ainsi déterminer précisément la version de Visual Studio qui a introduit un problème.  Pour un projet simple, il vaut mieux l'ouvrir dans la version la plus récente de Visual Studio et laisser l'Assistant convertir automatiquement le projet.  Si cela ne fonctionne pas, essayez de mettre à niveau une version à la fois, si vous avez accès aux versions appropriées de Visual Studio.  
  
 Notez que vous pouvez aussi exécuter devenv avec l'option `/Upgrade` sur la ligne de commande au lieu d'utiliser l'Assistant pour mettre à niveau vos projets.  Voir [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md).  Cette méthode est utile pour automatiser le processus de mise à niveau d'un grand nombre de projets.  
  
### Étape 1.Conversion du fichier projet  
 Quand vous ouvrez un ancien fichier projet dans Visual Studio 2015, Visual Studio propose de le convertir à la version la plus récente. C'est ce que nous avons choisi de faire.  La boîte de dialogue suivante s'est affichée :  
  
 ![Examen des modifications de projet et de solution](../porting/media/scribbleprojectupgrade.png "ScribbleProjectUpgrade")  
  
 Une erreur s'est produite. Le message nous informe que la cible Itanium n'est pas disponible et ne sera donc pas convertie.  
  
  **La plateforme 'Itanium' est absente du projet.  Toutes les configurations et leurs paramètres de configuration de fichier spécifiques à cette plateforme seront ignorés.  Si vous voulez que cette plateforme soit convertie, veillez à ce que la plateforme correspondante soit installée sous 'vctargetpath%\\platforms\\Itanium'.  Voulez\-vous continuer la conversion de ce projet sans cette plateforme ?**  Au moment de la création du projet Scribble précédent, Itanium était une plateforme cible importante.  La plateforme Windows ne prenant plus en charge Itanium, nous avons choisi de continuer sans la prise en charge de la plateforme Itanium.  
  
 Visual Studio affiche ensuite un rapport de migration qui répertorie tous les problèmes rencontrés avec l'ancien fichier projet.  
  
 ![Rapport de mise à niveau](../porting/media/scribblemigrationreport.png "ScribbleMigrationReport")  
  
 Dans ce cas, les problèmes signalés étaient tous des avertissements, et Visual Studio a effectué les modifications appropriées dans le fichier projet.  La grande différence en ce qui concerne le projet est que l'outil de build utilisé est maintenant msbuild au lieu de vcbuild.  Cette modification a été introduite dans Visual Studio 2010.  D'autres modifications ont été apportées, notamment une réorganisation de la séquence d'éléments dans le fichier projet.  Aucun des problèmes signalés ne nécessitait une attention particulière pour ce projet simple.  
  
### Étape 2.Préparation de la build  
 Avant de générer la build, nous vérifions l'ensemble d'outils de plateforme pour savoir quelle version du compilateur est utilisée par le système de projet.  Dans la boîte de dialogue des propriétés du projet, sous **Propriétés de configuration**, dans la catégorie **Général**, examinez la propriété **Ensemble d'outils de plateforme**.  La propriété indique la version de Visual Studio et le numéro de version des outils de plateforme, qui est ici v140 pour la version [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] des outils.  Quand vous convertissez un projet qui a été initialement compilé avec Visual C\+\+ 2010, 2012 ou 2013, l'ensemble d'outils n'est pas automatiquement mis à jour vers la version [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  Dans le cas de Scribble, la version que nous avons convertie avait été créée pour Visual Studio 2005. Il a donc fallu la convertir pour utiliser l'ensemble d'outils le plus récent.  
  
 Au moment de la build, le premier problème signalé concerne le code MBCS.  
  
  **error MSB8031:**  Le lien inclus dans le message d'erreur nous renvoie vers une rubrique sur l'utilisation déconseillée de MBCS dans Visual Studio 2013.  Par défaut, l'installation de MFC dans Visual C\+\+ 2013 n'inclut pas la version MBCS de MFC.  Cette version est nécessaire pour compiler ce projet dans sa forme actuelle.  Nous avons deux solutions : migrer le code pour utiliser Unicode ou télécharger et installer la version MBCS de MFC.  Si nous choisissons de télécharger la version MBCS de MFC, nous pouvons ajouter une définition de la macro NO\_WARN\_MBCS\_MFC\_DEPRECATION pour supprimer cet avertissement.  
  
 Avant de télécharger la version MBCS de MFC, lisez l'article [MFC MBCS DLL, complément](../mfc/mfc-mbcs-dll-add-on.md) et le blog VC sur l'utilisation déconseillée de la version MBCS de MFC. Ensuite, téléchargez cette version [ici](http://www.microsoft.com/download/details.aspx?id=44930).  Dans la boîte de dialogue des propriétés du projet, sous la catégorie **C\/C\+\+**, sous **Préprocesseur**, ajoutez la liste NO\_WARN\_MBCS\_MFC\_DEPRECATION à la liste des macros prédéfinies.  
  
 Pour passer au format Unicode, affichez les propriétés du projet, sous **Propriétés de configuration**, choisissez la section **Général** et recherchez la propriété **Jeu de caractères**.  Choisissez **Utiliser le jeu de caractères multioctet \(MBCS\)** au lieu de **Utiliser le jeu de caractères Unicode**.  Avec cette modification, les macros \_UNICODE et UNICODE sont maintenant définies alors que la macro \_MBCS ne l'est pas. Vous pouvez vérifier cela dans la boîte de dialogue des propriétés sous la catégorie **C\/C\+\+** de la propriété **Ligne de commande**.  
  
  **\/GS \/analyze\- \/W4 \/Gy \/Zc:wchar\_t \/Zi \/Gm\- \/O2 \/Ob1 \/Fd".  \\Release\\vc140.pdb" \/Zc:inline \/fp:precise \/D "\_AFXDLL" \/D "WIN32" \/D "NDEBUG" \/D "\_WINDOWS" \/D "\_UNICODE" \/D "UNICODE" \/errorReport:prompt \/GF \/WX \/Zc:forScope \/Gd \/Oy \/MD \/Fa".  \\Release\\" \/EHsc \/nologo \/Fo".  \\Release\\" \/Fp".  \\Release\\Scribble.pch"**  Bien que le projet Scribble n'a pas été configuré pour être compilé avec des caractères Unicode, il a déjà été écrit avec TCHAR au lieu de char. Il n'y a donc pas de modification à apporter.  Le projet a été compilé correctement avec le jeu de caractères Unicode.  
  
 Toutefois, il y a un autre problème.  Le compilateur indique que \_WINNT32\_WINNT n'est pas spécifié :  
  
  **\_WIN32\_WINNT non spécifié.  \_WIN32\_WINNT\_MAXVER pris par défaut \(voir WinSDKVer.h\)**  Ceci n'est pas une erreur, mais un avertissement très fréquent pendant la mise à niveau d'un projet Visual C\+\+.  Il s'agit de la macro qui définit la version de Windows la plus ancienne sur laquelle notre application s'exécutera.  Si nous ignorons l'avertissement, nous acceptons la valeur par défaut, \_WIN32\_WINNT\_MAXVER, qui correspond à la version actuelle de Windows.  Pour obtenir un tableau des valeurs possibles, voir [Utilisation des en\-têtes Windows](https://msdn.microsoft.com/en-us/library/aa383745.aspx).  Par exemple, nous pouvons choisir de l'exécuter sur toutes les versions à partir de Vista.  
  
```  
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
 Si le code utilise des parties de l'API Windows qui ne sont pas disponibles dans la version de Windows spécifiée avec cette macro, cela produit une erreur de compilateur.  Dans le cas de Scribble, il n'y a pas d'erreur.  
  
### Étape 3.Test et débogage  
 Comme il n'existe pas de suite de tests, nous avons simplement démarré l'application et testé ses fonctionnalités manuellement via l'interface utilisateur.  Nous n'avons observé aucun problème.  
  
### Étape 4.Amélioration du code  
 Vous avez effectué la migration vers Visual Studio 2015. Maintenant, vous voudrez probablement apporter quelques modifications pour exploiter au mieux les nouvelles fonctionnalités C\+\+.  La version actuelle du compilateur Visual C\+\+ est nettement plus conforme à la norme C\+\+ que les versions précédentes. Si vous envisagez de modifier votre code pour le sécuriser ou le rendre davantage compatible avec d'autres compilateurs et systèmes d'exploitation, étudiez les améliorations à apporter.  
  
## Étapes suivantes  
 Scribble était une petite application de bureau Windows, simple, que nous avons pu facilement convertir.  De nombreuses applications similaires seront tout aussi faciles à convertir vers la nouvelle version.  La mise à niveau prendra plus de temps pour les applications plus complexes, notamment celles qui contiennent beaucoup plus de lignes de code, du code hérité plus ancien qui n'est sans doute plus conforme aux normes de conception actuelles, plusieurs projets et bibliothèques, des étapes de build personnalisée ou des builds automatisées par script complexes.  Continuez avec l'[exemple suivant](../porting/porting-guide-com-spy.md), une application ATL\/COM appelée COM Spy.  
  
## Voir aussi  
 [Portage et mise à niveau : exemples et études de cas](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Exemple suivant : COM Spy](../porting/porting-guide-com-spy.md)
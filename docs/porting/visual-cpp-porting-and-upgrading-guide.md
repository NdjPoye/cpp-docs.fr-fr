---
title: "Guide du portage et de la mise &#224; niveau de Visual&#160;C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
caps.latest.revision: 8
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Guide du portage et de la mise &#224; niveau de Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique est destinée à vous guider lors de la mise à niveau du code Visual C\+\+.  Elle explique comment convertir le code pour qu'il se compile et s'exécute correctement sur une version plus récente des outils, et comment tirer parti des nouvelles fonctionnalités de langage et de Visual Studio.  Cette rubrique inclut également des informations sur la migration des applications héritées vers des plateformes plus récentes.  
  
## Raisons justifiant la mise à niveau du code Visual C\+\+  
 Vous devez envisager la mise à niveau de votre code pour les raisons suivantes :  
  
-   Code plus rapide, grâce à de nouvelles optimisations apportées au compilateur.  
  
-   Builds plus rapides, grâce à l'amélioration des performances du compilateur.  
  
-   Nouvelles fonctionnalités de langage.  Visual C\+\+ implémente désormais de nombreuses fonctionnalités conformes aux normes C\+\+ les plus récentes.  
  
-   Sécurité renforcée,  grâce aux fonctionnalités de sécurité, telles que la protection du flux de contrôle.  
  
### Déplacement de votre code  
 Dans le cadre de la mise à niveau, commencez par faire le point sur le code et les projets de votre application.  Votre application a\-t\-elle été développée avec Visual Studio ?  Dans ce cas, identifiez les projets concernés.  Utilisez\-vous des scripts de compilation personnalisés ?  Si vous utilisez des scripts de compilation personnalisés au lieu du système de génération de Visual Studio, vous aurez plus de tâches à effectuer vous\-même pendant la mise à niveau, car Visual Studio ne pourra pas mettre à jour vos fichiers projet et paramètres de génération automatiquement.  
  
 Le format du système de génération et des fichiers projet a changé dans Visual Studio. Depuis Visual Studio 2010, MSBuild a remplacé vcbuild qui était utilisé dans Visual Studio 2008 et les versions antérieures.  Si vous effectuez la mise à niveau d'une solution créée dans une version antérieure à 2010 et que vous utilisez un système de génération très personnalisé, le processus de mise à niveau sera sans doute plus complexe.  Si vous mettez à niveau une solution créée dans Visual Studio 2010 ou une version ultérieure, votre projet est déjà basé sur MSBuild. Le processus de mise à niveau et de compilation de votre application sera donc plus facile en principe.  
  
 Si vous n'utilisez pas le système de génération de Visual Studio, vous devez envisager la mise à niveau vers MSBuild.  Si vous faites ce choix, vous pourrez effectuer les futures mises à niveau plus rapidement et vous aurez plus facilement accès à divers services, tels que Visual Studio Online.  MSBuild prend en charge toutes les plateformes cibles prises en charge par Visual Studio.  
  
### Déplacement de projets Visual Studio  
 Pour les projets de grande taille, il peut être préférable d'effectuer la mise à niveau d'une seule version de Visual Studio à la fois, car vous pourrez ainsi mieux identifier la version qui a introduit une modification avec rupture empêchant votre code de s'exécuter correctement.  
  
 Pour commencer la mise à niveau d'un projet ou d'une solution, ouvrez simplement la solution dans la nouvelle version de Visual Studio et suivez les indications affichées.  Quand vous mettez à niveau un projet, un rapport de mise à niveau est généré et enregistré dans votre dossier de projet sous le nom UpgradeLog.htm.  Ce rapport récapitule les problèmes rencontrés pendant la mise à niveau, et fournit des informations sur les modifications apportées ou sur les problèmes qui n'ont pas pu être résolus automatiquement.  
  
1.  Propriétés de projet  
  
2.  Fichiers Include  
  
3.  Code qui ne se compile plus correctement en raison de la mise en conformité du compilateur.  
  
4.  Code qui fait appel à des fonctionnalités Visual Studio ou Windows qui ne sont plus disponibles, ou à des fichiers d'en\-tête qui ne sont pas inclus dans une installation par défaut de Visual Studio ou qui ont été supprimés du produit.  
  
5.  Code qui ne se compile plus à cause des modifications apportées aux API \(par exemple, API renommées, signatures de fonction modifiées ou fonctions déconseillées\).  
  
6.  Code qui ne se compile plus à cause des modifications apportées aux diagnostics \(par exemple, un avertissement transformé en erreur\).  
  
7.  Erreurs de l'éditeur de liens dues aux modifications de bibliothèques, en particulier quand \/NODEFAULTLIB est utilisé.  
  
8.  Erreurs d'exécution ou résultats inattendus dus à des changements de comportement.  
  
9. Erreurs elles\-mêmes provoquées par des erreurs introduites dans les outils.  Si vous rencontrez un problème, signalez\-le à l'équipe Visual C\+\+ via vos modes de contact du support technique habituels ou dans le [Centre des commentaires Visual Studio](http://connect.microsoft.com/VisualStudio/Feedback).  
  
 Certaines modifications sont inévitables pour résoudre les erreurs de compilateur, d'autres sont facultatives dans un processus de mise à niveau. Par exemple :  
  
1.  L'affichage de nouveaux avertissements peut être le signe qu'un nettoyage de votre code est nécessaire.  En fonction des diagnostics spécifiques, cela peut améliorer la portabilité, la conformité aux normes et la sécurité de votre code.  
  
2.  Vous pouvez exploiter les nouvelles fonctionnalités du compilateur, telles que l'option de compilateur [\/guard:cf \(Activer la protection du flux de contrôle\)](../build/reference/guard-enable-control-flow-guard.md), qui permet de vérifier si du code non autorisé est exécuté.  
  
3.  Vous pouvez mettre à jour le code pour utiliser les nouvelles fonctionnalités de langage qui simplifient l'écriture du code, améliorer les performances de vos programmes, utiliser les bibliothèques actuelles, et rendre le code conforme aux normes et meilleures pratiques récentes.  
  
 Une fois que vous avez mis à niveau \(et testé\) votre projet, vous pouvez également songer à améliorer encore votre code ou planifier la future orientation de votre code, ou même reconsidérer l'architecture de votre projet.  Est\-ce important que votre code puisse s'exécuter sur d'autres plateformes ?  Et sur quelles plateformes ?  C\+\+ est un langage normalisé conçu pour faciliter le développement d'applications multiplateforme et garantir leur portabilité. Pourtant, le code de nombreuses applications Windows dépend encore étroitement de la plate\-forme Windows.  Souhaitez\-vous refactoriser votre code pour isoler les parties de code qui sont le plus liées à la plateforme Windows ?  
  
 Qu'en est\-il de votre interface utilisateur ?  Si vous utilisez MFC, vous pouvez mettre à jour l'interface utilisateur.  Utilisez\-vous l'une des nouvelles fonctionnalités MFC introduites dans Visual Studio 2008 sous forme de Feature Pack ?  Si vous souhaitez seulement donner à votre application une apparence plus actuelle, sans réécrire entièrement le code, vous pouvez envisager d'utiliser des API de ruban dans MFC ou certaines nouvelles fonctionnalités de MFC.  
  
 Pour ajouter une nouvelle interface utilisateur de Bureau Windows, vous pouvez utiliser C\+\+\/CX \(extensions du composant\) ou ajouter du code managé en C\# et une couche d'interopérabilité en C\+\+\/CLI pour lier C\# à votre code natif.  
  
 Ou bien, vous avez peut\-être maintenant de nouvelles spécifications à respecter, ou vous voulez préparer votre application pour le ciblage d'autres plateformes que le Bureau Windows, telles que Windows Phone ou des appareils Android.  Vous pouvez déplacer votre code d'interface utilisateur vers une bibliothèque d'interface utilisateur multiplateforme.  Avec toutes ces infrastructures d'interface utilisateur, vous pouvez cibler divers appareils, tout en continuant à utiliser Visual Studio et le débogueur Visual Studio comme environnement de développement.  
  
## Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Mise à niveau de projets à partir de versions antérieures de Visual C\+\+](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Explique comment utiliser des projets créés dans les versions antérieures de Visual C\+\+.|  
|[Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)|Répertorie les modifications apportées aux bibliothèques Visual C\+\+ et outils de génération qui pourraient vous contraindre à modifier votre code.|  
|[Portage et mise à niveau : exemples et études de cas](../porting/porting-and-upgrading-examples-and-case-studies.md)|Dans cette section, nous avons déplacé et mis à niveau plusieurs exemples et applications, puis présenté nos expériences et résultats.  Cela vous donnera une idée de ce qu'impliquent les processus de déplacement et de mise à niveau.  Nous donnons des conseils et astuces à suivre pendant toute la mise à niveau, et indiquons des solutions pour corriger certaines erreurs courantes.|  
|[Portage vers la plateforme Windows universelle](../porting/porting-to-the-universal-windows-platform-cpp.md)|Contient des informations sur le déplacement de code vers Windows 10|  
|[Introduction à Visual C\+\+ pour les utilisateurs UNIX](../porting/introduction-to-visual-cpp-for-unix-users.md)|Fournit des informations aux utilisateurs UNIX qui débutent et souhaitent être plus productifs avec [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].|  
|[Portage d'UNIX vers Win32](../porting/porting-from-unix-to-win32.md)|Présente les différentes options pour migrer des applications UNIX vers Windows.|  
|[Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)|Explique en détail comment mettre à niveau la syntaxe de vos extensions managées pour C\+\+ par rapport à la nouvelle syntaxe.  Pour plus d'informations, voir [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).|  
  
## Voir aussi  
 [Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)
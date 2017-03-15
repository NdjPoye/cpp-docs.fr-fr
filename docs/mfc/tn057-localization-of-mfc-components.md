---
title: "TN057&#160;: localisation des composants MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.components"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "composants (MFC), localiser"
  - "DLL (C++), localiser des MFC"
  - "localisation (C++), composants MFC"
  - "localisation (C++), ressources MFC"
  - "localisation (C++), ressources"
  - "DLL MFC (C++), localiser"
  - "ressources (MFC), localisation"
  - "TN057"
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN057&#160;: localisation des composants MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit certaines conceptions et les procédures permettant de localiser votre composant, si c'est une application ou une commande OLE ou une DLL qui utilise MFC.  
  
## Vue d'ensemble  
 Il existe réellement deux problèmes à résoudre en localisant un composant qui utilise MFC.  D'abord, vous devez localiser vos ressources propres — chaînes, dialogues, et d'autres ressources qui sont spécifiques à votre composant.  La plupart des composants créés à l'aide de MFC incluent également et utilisent plusieurs ressources définies par MFC.  Vous devez fournir des ressources localisés en MFC.  Heureusement, plusieurs langues sont déjà fournis par MFC lui\-même.  
  
 De plus, votre composant doit être préparé à s'exécuter dans son environnement cible \(européen environnement ou DBCS\- activé\).  Dans la plupart des cas, cela dépend du traitement des caractères du bit le plus élevé défini correctement par votre application et la gestion des chaînes avec des caractères en octets.  MFC est activé, par défaut, pour les deux environnements, afin qu'il est possible d'avoir un seul système binaire mondial utilisé pour toutes les plateformes avec uniquement des ressources branchées au moment de l'installation.  
  
## Recherche des ressources du composant  
 Rechercher votre application ou DLL doit impliquer simplement de remplacer les ressources par d'autres qui correspondent à la langue\-cible.  Pour vos ressources propres, il est relativement simple : modifiez les ressources dans l'éditeur de ressources et générer votre application.  Si votre code doit être écrit correctement il n'y aura pas de caractères ou texte que vous trouverez codé de manière irréversible dans votre code source C\+\+ – toute localisation peut être effectuée en modifiant simplement des ressources.  En fait, vous pouvez implémenter votre composant de telle sorte que ce qui est fourni par une version localisée n'implique pas même une génération de code d'origine.  C'est plus complexe, mais cela en vaut la peine et c'est le mécanisme sélectionné pour MFC lui\-même.  Il est également possible de trouver une application en chargeant le fichier EXE ou le fichier .dll dans l'éditeur de ressources et en modifiant les ressources.  Si possible, cela requiert le reapplication de modifications chaque fois que vous créez une nouvelle version de votre application.  
  
 Une façon d'éviter cela est de rechercher toutes les ressources dans une DLL distincte, parfois appelée une DLL satellite.  Cette DLL est alors chargé dynamiquement pendant l'exécution et les ressources sont chargées à partir de cette DLL au lieu du module principal avec tout votre code.  MFC gère directement la méthode.  Examinez une application appelée MYAPP.EXE ; il peut contenir toutes ses ressources situées dans un MYRES.DLL appelé par la DLL.  Dans `InitInstance` de l'application il doit effectuer les opérations suivantes pour charger cette DLL et pour générer MFC aux ressources en charge de l'emplacement :  
  
```  
CMyApp::InitInstance()  
{  
   // one of the first things in the init code  
   HINSTANCE hInst = LoadLibrary("myres.dll");  
   if (hInst != NULL)  
      AfxSetResourceHandle(hInst);  
  
   // other initialization code would follow  
   .  
   .  
   .  
}  
```  
  
 À compter de ce moment, MFC charge les ressources de cette DLL au lieu de myapp.exe.  Toutes les ressources, toutefois, doivent être présentes dans cette DLL ; MFC ne trouve pas l'instance d'application à la recherche d'une ressource donnée.  Cette technique s'applique aussi bien aux DLL standards qu'aux commandes OLE.  Le programme d'installation copierait la version appropriée de MYRES.DLL selon lequel les paramètres régionaux de ressource que l'utilisateur souhaiterait.  
  
 Il est relativement facile de créer une DLL de ressource uniquement.  Vous créez un projet de DLL, lui ajoutez votre fichier .RC, puis ajoutez les ressources nécessaires.  Si vous avez un projet existant qui n'utilise pas cette technique, vous pouvez copier les ressources de ce projet.  Après avoir ajouté le fichier de ressources au projet, vous êtes prêt à presque générer le projet.  La seule chose à faire est de définir les options de l'éditeur de liens pour inclure **\/NOENTRY**.  Cela indique à l'éditeur de liens que la DLL n'a aucun point d'entrée – étant donné qu'il n'a aucun code, il n'a aucun point d'entrée.  
  
> [!NOTE]
>  L'éditeur de ressources dans Visual C\+\+ 4,0 et les versions ultérieures de supports par plusieurs .RC fichier.  Cela peut rendre très facile la gestion de votre emplacement dans un projet.  Les ressources pour chaque langue sont contrôlées par des directives du préprocesseur générées par l'éditeur de ressources.  
  
## Utilisation des ressources localisées fournies par MFC  
 Toutes les applications de MFC lorsque vous créez réutilisent deux choses de MFC : le code et les ressources.  Autrement dit, MFC a plusieurs messages d'erreur, dialogues prédéfinis, et d'autres ressources utilisées par les classes de MFC.  Pour trouver entièrement votre application, vous devez rechercher non seulement les ressources de votre application, mais également des ressources provenant directement de MFC.  MFC fournit plusieurs des fichiers de ressources de langue automatiquement, de sorte que si la langue que vous visez est une des langues déjà prises en charge par MFC, vous devez simplement que vous utilisez ces ressources localisées.  
  
 À compter de ces écritures, MFC prend en charge le Chinois, l'Allemand, l'Espagnol, le Français, l'Italien, le Japonais, et le Coréen.  Les fichiers qui contiennent ces versions localisées sont dans des répertoires de MFC INCLUDE\\\\ L.\* \(les « L » représente localisé\).  Les fichiers allemands sont dans MFC INCLUDE\\\\ L.DEU, par exemple.  Pour générer votre application pour utiliser les fichiers RC au lieu des fichiers situés dans MFC\\INCLUDE, ajoutez `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` à la ligne de commande RC \(il s'agit d'un exemple ; vous devez remplacer les paramètres régionaux du tableau ainsi que du dossier dans lequel vous avez installé Visual C\+\+\).  
  
 L'instruction ci\-dessus fonctionne si vos applications se lient statiquement avec MFC.  La plupart des applications se lient dynamiquement \(parce que c'est la valeur par défaut d'AppWizard\).  Dans ce scénario, non seulement le code est dynamiquement lié – mais les ressources également.  Par conséquent, vous pouvez localiser vos ressources dans votre application, mais les ressources d'implémentation MFC seront encore chargées de MFC7x.DLL \(ou version ultérieure\) ou de MFC7xLOC.DLL s'il existe.  Vous pouvez considérer ceci sous deux différents angles.  
  
 L'approche plus complexe est de fournir l'un des MFC7xLOC.DLLs du fichier \(tel que MFC7xDEU, pour l'Allemand, le MFC7xESP.DLL pour l'Espagnol, etc.\), ou une version ultérieure, et installer le MFC7xLOC.DLL approprié dans le répertoire système lorsque l'utilisateur installe votre application.  Cela peut s'avérer très complexe pour le développeur et l'utilisateur final et par conséquent, ce n'est pas recommandée.  Consultez la [Note technique 56](../mfc/tn056-installation-of-localized-mfc-components.md) pour plus d'informations sur cette technique et ses oppositions.  
  
 L'approche la plus simple et plus sûre consiste à inclure les ressources localisées en MFC dans votre application ou DLL lui\-même \(ou son DLL satellite si vous utilisez un\).  Cela évite les problèmes d'installation correcte de MFC7xLOC.DLL.  Pour ce faire, procédez avec la même instruction que le cas statique fourni ci\-dessus \(définissant la ligne de commande RC correctement pour afficher les ressources localisées\), mais vous devez également supprimer le `/D_AFXDLL` défini ajouté par AppWizard.  Lorsque `/D_AFXDLL` est défini, AFXRES.H \(et les autres fichiers de MFC SERVER\) ne définissent pas réellement une quelconque ressource \(parce qu'elles sont extraites des DLLs MFC à la place\).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
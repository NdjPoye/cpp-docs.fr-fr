---
title: "DLL d&#39;extension | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL (bibliothèque)"
  - "DLL (C++), extension"
  - "DLL d'extension (C++)"
  - "DLL d'extension (C++), à propos des DLL d'extension"
  - "mémoire (C++), DLL"
  - "DLL MFC (C++), DLL d'extension"
  - "DLL d'extension MFC (C++)"
  - "partager des ressources (C++)"
  - "versions DLL partagées (C++)"
  - "ressources partagées (C++)"
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL d&#39;extension
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une DLL d'extension des MFC est une DLL qui implémente généralement des classes réutilisables dérivées de classes existantes de la bibliothèque MFC.  
  
 Une DLL d'extension des MFC présente les fonctionnalités et répond aux conditions suivantes :  
  
-   L'exécutable client doit être une application MFC compilée avec **\_AFXDLL** défini.  
  
-   Une DLL d'extension peut également être utilisée par une DLL normale liée de manière dynamique aux MFC.  
  
-   Les DLL d'extension doivent être compilées avec `_AFXEXT` définie.  Cela force le symbole **\_AFXDLL** à être également défini et garantit l'extraction des déclarations appropriées à partir des fichiers d'en\-tête MFC.  Cela assure également que **AFX\_EXT\_CLASS** sera défini en tant que **\_\_declspec\(dllexport\)** lors de la génération de la DLL, ce qui est nécessaire si vous utilisez cette macro pour déclarer les classes dans votre DLL d'extension.  
  
-   Les DLL d'extension ne doivent pas instancier une classe dérivée de `CWinApp`, mais doivent se fier à l'application cliente \(ou DLL\) pour la fourniture de cet objet.  
  
-   Les DLL d'extension doivent, toutefois, fournir une fonction `DllMain` et se charger de toute tâche d'initialisation requise.  
  
 Les DLL d'extension sont générées à l'aide de la version bibliothèque de liens dynamiques des MFC \(appelée également version partagée des MFC\).  Seuls les exécutables MFC \(applications ou DLL normales\) qui sont générés à l'aide de la version partagée des MFC peuvent utiliser une DLL d'extension.  L'application cliente et la DLL d'extension doivent utiliser la même version de MFCx0.dll.  Avec une DLL d'extension, vous pouvez dériver de nouvelles classes personnalisées à partir des MFC puis offrir cette version étendue des MFC aux applications qui appellent votre DLL.  
  
 Les DLL d'extension peuvent également être utilisées pour passer des objets dérivés des MFC entre l'application et la DLL.  Les fonctions membres associées à l'objet passé existent dans le module où l'objet a été créé.  Comme ces fonctions sont exportées correctement lorsque vous utilisez la version DLL partagée de MFC, vous pouvez passer librement des pointeurs désignant des objets MFC ou dérivés des MFC entre une application et les DLL d'extension chargées par elle.  
  
 Une DLL d'extension MFC utilise une version partagée de MFC de la même façon qu'une application utilise la version DLL partagée de MFC, avec quelques remarques supplémentaires :  
  
-   Elle ne dispose pas d'un objet dérivé de `CWinApp`.  Elle doit collaborer avec l'objet dérivé de `CWinApp` de l'application cliente.  Cela signifie que l'application cliente possède la pompe de messages principale, la boucle inactive, etc.  
  
-   Elle appelle `AfxInitExtensionModule` dans sa fonction `DllMain`.  La valeur de retour de cette fonction doit être vérifiée.  Si une valeur zéro est retournée à partir de `AfxInitExtensionModule`, retournez 0 à partir de votre fonction `DllMain`.  
  
-   Elle crée un objet **CDynLinkLibrary** pendant l'initialisation si la DLL d'extension souhaite exporter des ressources ou des objets `CRuntimeClass` vers l'application.  
  
 Avant la version 4.0 des MFC, ce type de DLL s'appelait AFXDLL.  AFXDLL désigne le symbole de préprocesseur **\_AFXDLL** qui est défini lors de la génération de la DLL.  
  
 Les bibliothèques d'importation de la version partagée des MFC sont nommées selon la convention décrite dans la rubrique [Conventions d'attribution de noms aux DLL MFC](../build/naming-conventions-for-mfc-dlls.md).  Visual C\+\+ fournit des versions prégénérées des DLL MFC, plus un certain nombre de DLL non\-MFC que vous pouvez utiliser et distribuer avec vos applications.  Celles\-ci sont documentées dans le fichier Redist.txt, qui est installé dans le dossier Program Files\\Microsoft Visual Studio.  
  
 Si vous exportez à l'aide d'un fichier .def, placez le code suivant au début et à la fin du fichier d'en\-tête :  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Ces quatre lignes garantissent que votre code sera compilé correctement pour une DLL d'extension.  Si vous les omettez, la DLL risque d'être compilée ou liée incorrectement.  
  
 Si vous devez passer un pointeur désignant un objet MFC ou un objet dérivé des MFC vers ou à partir d'une DLL MFC, celle\-ci doit être une DLL d'extension.  Les fonctions membres associées à l'objet passé existent dans le module où l'objet a été créé.  Comme ces fonctions sont exportées correctement lorsque vous utilisez la version DLL partagée de MFC, vous pouvez passer librement des pointeurs désignant des objets MFC ou dérivés des MFC entre une application et les DLL d'extension chargées par elle.  
  
 Compte tenu des problèmes d'exportation et d'amputation des noms du C\+\+, la liste d'exportation à partir d'une DLL d'extension peut varier entre la version Debug et la version commerciale pour la même DLL et les DLL de plateformes différentes.  La MFCx0.dll commerciale compte près de 2 000 points d'entrée exportés, alors que la MFCx0D.dll de débogage en possède près de 3 000.  
  
## Gestion de la mémoire  
 MFCx0.dll et toutes les DLL d'extension chargées dans l'espace d'adressage d'une application cliente utilisent les mêmes modules d'allocation de mémoire, de chargement de ressources et autres états globaux MFC que si elles faisaient partie de la même application.  Ceci est important car les bibliothèques des DLL non\-MFC et les DLL normales font exactement le contraire et s'assurent que chaque DLL affecte une partie de son propre pool de mémoires.  
  
 Si une DLL d'extension alloue de la mémoire, cette mémoire peut alors être librement mélangée avec tout autre objet alloué par l'application.  De même, si une application liée de manière dynamique aux MFC se bloque, la protection du système d'exploitation assure l'intégrité de toute autre application MFC partageant la DLL.  
  
 D'autres états MFC globaux, comme le fichier exécutable en cours à partir duquel il faut charger des ressources, sont également partagés entre l'application cliente et toutes les DLL d'extension MFC ainsi que MFCx0.dll elle\-même.  
  
## Partage des ressources et des classes  
 L'exportation des ressources s'effectue par l'intermédiaire d'une liste de ressources.  Chaque application contient une seule liste liée d'objets **CDynLinkLibrary**.  Lors de la recherche d'une ressource, la plupart des implémentations MFC standard qui chargent des ressources examinent d'abord le module de ressources en cours \(`AfxGetResourceHandle`\) et, si la ressource est introuvable, parcourent la liste des objets **CDynLinkLibrary** en vue d'essayer de charger la ressource demandée.  
  
 Le fait de parcourir la liste a pour inconvénient de ralentir les opérations et d'exiger la gestion de plages d'ID de ressources.  L'avantage c'est qu'une application cliente qui lie à plusieurs DLL d'extension peut utiliser les ressources fournies par la DLL sans devoir spécifier le handle d'instance de DLL.  `AfxFindResourceHandle` est une API utilisée pour accompagner la liste des ressources pour rechercher une correspondance donnée.  Elle prend le nom et le type d'une ressource et retourne le handle de la ressource où elle a été trouvée en premier lieu \(ou la valeur NULL\).  
  
 Si vous ne souhaitez pas parcourir la liste mais seulement charger les ressources à partir d'un emplacement spécifique, utilisez les fonctions `AfxGetResourceHandle` et `AfxSetResourceHandle` pour enregistrer l'ancien handle et définir le nouveau handle.  Veillez à restaurer l'ancien handle de la ressource avant de retourner à l'application cliente.  Pour obtenir un exemple d'utilisation de cette approche en vue de charger explicitement un menu, consultez le fichier .cpp Testdll2 dans l'exemple MFC [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90).  
  
 La création dynamique d'objets MFC dotés d'un nom MFC est similaire.  Le mécanisme de désérialisation des objets MFC exige que tous les objets `CRuntimeClass` soient enregistrés afin qu'il puisse reconstruire en créant de manière dynamique les objets C\+\+ du type requis sur la base de ce qui était stocké précédemment.  
  
 Dans le cas de l'exemple MFC [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90), la liste ressemble à ceci :  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
           MFCOxxD.DLL                |  
               |                      |  
           MFCDxxD.DLL                |  
               |                      |  
            MFCxxD.DLL            MFCxx.DLL  
```  
  
 où *xx* est le numéro de version ; par exemple, 42 représente la version 4.2.  
  
 MFCxx.dll occupe généralement la dernière position sur la liste des ressources et des classes.  MFCxx.dll inclut toutes les ressources MFC standard, y compris les chaînes des invites de tous les ID de commande standard.  Le fait de la placer à la fin de la liste permet à toutes les DLL et à l'application cliente elle\-même de ne pas avoir leur propre copie des ressources MFC standard, mais de se fier plutôt aux ressources partagées dans la MFCxx.dll.  
  
 Le fait de fusionner les ressources et les noms de classes de toutes les DLL dans l'espace de noms de l'application cliente a pour inconvénient de vous obliger à être vigilant avec les ID ou les noms que vous sélectionnez.  
  
 L'exemple [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) gère l'espace de noms des ressources partagées en utilisant plusieurs fichiers d'en\-tête.  
  
 Si la DLL d'extension MFC doit gérer des données supplémentaires pour chaque application, vous pouvez dériver une nouvelle classe à partir de **CDynLinkLibrary** et la créer dans `DllMain`.  Au moment de l'exécution, la DLL peut consulter la liste des objets **CDynLinkLibrary** de l'application en cours pour rechercher celui qui correspond à cette DLL d'extension particulière.  
  
### Que voulez\-vous faire ?  
  
-   [Initialiser une DLL d'extension](../build/initializing-extension-dlls.md)  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Conseils relatifs à l'utilisation des fichiers de ressources partagés](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [Version DLL de MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)
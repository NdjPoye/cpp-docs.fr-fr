---
title: "Initialisation d&#39;une DLL | Microsoft Docs"
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
helpviewer_keywords: 
  - "DLL (C++), initialiser"
  - "initialiser les DLL"
  - "code de terminaison (C++)"
ms.assetid: f655c5ff-ab5b-493a-a1da-4d1074e60c5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisation d&#39;une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En général, la DLL possède un code d'initialisation \(comme l'allocation de mémoire\) qui doit s'exécuter lors du chargement de la DLL.  Lorsque vous utilisez Visual C\+\+, l'emplacement où vous ajoutez le code d'initialisation de la DLL dépend du type de DLL que vous générez.  Si vous n'avez pas besoin d'ajouter un code d'initialisation ou d'arrêt, vous n'avez rien de spécial à faire lors de la génération de la DLL.  Si vous devez initialiser la DLL, le tableau suivant indique où ajouter le code.  
  
|Type de DLL|Où ajouter le code d'initialisation et d'arrêt|  
|-----------------|----------------------------------------------------|  
|DLL normale|Dans les fonctions `InitInstance` et `ExitInstance` de l'objet `CWinApp` de la DLL.|  
|DLL d'extension|Dans la fonction `DllMain` générée par l'Assistant DLL MFC.|  
|DLL non\-MFC|Dans une fonction appelée `DllMain` que vous fournissez.|  
  
 En environnement Win32, toutes les DLL peuvent contenir une fonction de point d'entrée facultative \(généralement dénommée `DllMain`\) qui est appelée à la fois pour l'initialisation et l'arrêt.  Cela vous donne la possibilité d'allouer ou de libérer des ressources supplémentaires, en fonction des besoins.  Windows appelle la fonction de point d'entrée dans quatre situations : attachement de processus, détachement de processus, attachement de thread et détachement de thread.  
  
 La bibliothèque Runtime C fournit une fonction de point d'entrée dénommée **\_DllMainCRTStartup** et appelle `DllMain`.  Selon le type de DLL, vous devez avoir une fonction appelée `DllMain` dans le code source ou utiliser le `DllMain` fourni dans la bibliothèque MFC.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser des DLL normales](../build/initializing-regular-dlls.md)  
  
-   [Initialiser des DLL d'extension](../build/initializing-extension-dlls.md)  
  
-   [Initialiser des DLL non\-MFC](../build/initializing-non-mfc-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Comportement de la bibliothèque Runtime C et DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [\<caps:sentence id\="tgt24" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>La spécification de fonction pour DllMain \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Fonction de point d'entrée de bibliothèque de liens dynamiques \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)
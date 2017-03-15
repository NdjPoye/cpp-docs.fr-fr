---
title: "CWinApp&#160;: classe d&#39;application | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application (classe)"
  - "CWinApp (classe), CWinThread"
  - "CWinApp (classe), multithreading"
  - "CWinApp (classe), WinMain"
  - "CWinThread (classe), et CWinApp"
  - "InitApplication (méthode)"
  - "MFC (C++), WinMain et"
  - "WinMain (méthode)"
  - "WinMain (méthode), dans MFC"
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CWinApp&#160;: classe d&#39;application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe d'application principale de MFC encapsule l'initialisation, l'exécution, et l'arrêt d'une demande de système d'exploitation Windows.  Une application générée sur l'infrastructure doit avoir un seul objet d'une classe dérivée de [CWinApp](../mfc/reference/cwinapp-class.md).  Cet objet est créé avant que les fenêtres soient créées.  
  
 `CWinApp` est dérivé de `CWinThread`, qui représente le thread principal de l'exécution de l'application, qui peut avoir un ou plusieurs threads.  Dans les versions récentes de MFC, `InitInstance`, **Exécuter**, `ExitInstance`, les fonctions membres de `OnIdle` sont réellement dans la `CWinThread`classe.  Ces fonctions sont décrites comme si elles étaient des membres de `CWinApp` à la place, la discussion affecte le rôle de l'objet comme objet d'application et non comme thread principal.  
  
> [!NOTE]
>  La classe d'application constitue le thread principal de l'application de l'exécution.  Utilisation des fonctions d'API Win32, vous pouvez également créer des threads secondaires de l'exécution.  Ces threads peuvent utiliser la bibliothèque MFC.  \(Pour plus d'informations, consultez [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Comme tout programme du système d'exploitation Windows, votre application framework possède une fonction de `WinMain`.  Dans une application d'infrastructure, toutefois, vous n'entrez pas `WinMain`.  Elle est fournie par la bibliothèque de classes et est appelée lorsque l'application démarre.  `WinMain` fournit des services standard tels que les classes windows.  Elle appelle les fonctions membres de l'objet d'application pour initialiser et exécuter l'application. \(Vous pouvez personnaliser `WinMain` en remplaçant les fonctions membres de `CWinApp` que `WinMain` appelle.\)  
  
 Pour initialiser l'application, `WinMain` appelle les fonctions membres de `InitApplication` et de `InitInstance` de votre objet d'application.  Pour effectuer une boucle de message de l'application, `WinMain` appelle la fonction membre du **Exécuter**.  Sur l'arrêt, `WinMain` appelle la fonction membre de `ExitInstance` de l'objet d'application.  
  
> [!NOTE]
>  Les noms affichés en **gras** dans cette documentation indiquent les éléments fournis par la bibliothèque MFC et Visual C\+\+.  Les noms affichés dans le type de `monospaced` indiquent les éléments que vous créez ou remplacez.  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [CWinApp et l'Assistant Application MFC](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Fonctions membres CWinApp remplaçables](../mfc/overridable-cwinapp-member-functions.md)   
 [Services CWinApp spéciaux](../mfc/special-cwinapp-services.md)
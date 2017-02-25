---
title: "Initialisation de DLL normales | Microsoft Docs"
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
  - "DLL (C++), normales"
  - "initialiser les DLL"
  - "DLL normales (C++), initialiser"
ms.assetid: f1f091d1-bb91-468a-94f4-3c554657b8fc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisation de DLL normales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la mesure où elles disposent d'un objet `CWinApp`, les DLL normales doivent réaliser leurs tâches d'initialisation et d'arrêt au même endroit qu'une application MFC : dans les fonctions membres `InitInstance` et **ExitInstance** de la classe dérivée de `CWinApp` de la DLL.  Comme la bibliothèque MFC fournit une fonction `DllMain` qui est appelée par **\_DllMainCRTStartup** pour **PROCESS\_ATTACH** et **PROCESS\_DETACH**, vous ne devez pas écrire votre propre fonction `DllMain`.  La fonction `DllMain` fournit par la bibliothèque MFC appelle `InitInstance` lors du chargement de la DLL et `ExitInstance` avant son déchargement.  
  
 Une DLL normale peut assurer le suivi de plusieurs threads en appelant [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) et [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) dans sa fonction `InitInstance`.  Ces fonctions permettent à la DLL de suivre les données spécifiques des threads.  
  
 Dans la DLL normale liée de manière dynamique aux MFC, si vous assurez une prise en charge de ressources OLE MFC, base de données MFC \(ou DAO\) ou sockets MFC, les DLL d'extension de débogage MFC MFCOxxD.dll, MFCDxxD.dll et MFCNxxD.dll \(où xx correspond au numéro de version\) sont, respectivement, liées de façon automatique.  Vous devez appeler l'une des fonctions d'initialisation prédéfinies suivantes pour chacune des DLL que vous utilisez dans `CWinApp::InitInstance` de votre DLL normale.  
  
|Type de prise en charge MFC|Fonction d'initialisation à appeler|  
|---------------------------------|-----------------------------------------|  
|OLE MFC \(MFCOxxD.dll\)|`AfxOleInitModule`|  
|Base de données MFC \(MFCDxxD.dll\)|`AfxDbInitModule`|  
|Sockets MFC \(MFCDxxD.dll\)|`AfxNetInitModule`|  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser des DLL d'extension](../build/initializing-extension-dlls.md)  
  
-   [Initialiser des DLL non\-MFC](../build/initializing-non-mfc-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Comportement de la bibliothèque Runtime C et DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="704731be78a1b2b43311fed62656e454" class\="tgtSentence"\>Processus et threads \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
-   [Wrappers de stockage local des threads \(note technique MFC 58\)](../mfc/tn058-mfc-module-state-implementation.md)  
  
## Voir aussi  
 [Initialisation d'une DLL](../build/initializing-a-dll.md)
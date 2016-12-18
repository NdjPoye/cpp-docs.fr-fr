---
title: "Une DLL MFC peut-elle cr&#233;er plusieurs threads&#160;? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), multithreading"
  - "DLL MFC (C++), multithreading"
  - "multithreading (C++), DLL"
  - "threads (MFC), DLL"
ms.assetid: 41d5b5e6-a7d3-42bf-b641-f1245abd1c59
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Une DLL MFC peut-elle cr&#233;er plusieurs threads&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sauf pendant l'initialisation, une DLL MFC peut créer de manière sécurisée plusieurs threads du moment qu'elle utilise des fonctions de stockage local des threads \(TLS, Thread Local Storage\) Win32 telles que **TlsAlloc** pour allouer un stockage local des threads.  Cependant, si une DLL MFC utilise **\_\_declspec\(thread\)** pour allouer un stockage local des threads, l'application cliente doit être liée implicitement à la DLL.  Si l'application cliente est liée de manière explicite à la DLL, l'appel à **LoadLibrary** ne réussira pas à charger la DLL.  Pour plus d'informations sur la création de threads multiples dans les DLL MFC, consultez l'article de la Base de connaissances \(en anglais\) « PRB: Calling LoadLibrary\(\) to Load a DLL That Has Static TLS » \(Q118816\).  
  
 Une DLL MFC qui crée un nouveau thread MFC pendant le démarrage cesse de répondre quand elle est chargée par une application.  Ce comportement se vérifie chaque fois qu'un thread est créé par un appel à `AfxBeginThread` ou à `CWinThread::CreateThread` dans :  
  
-   la fonction `InitInstance` d'un objet dérivé de `CWinApp` dans une DLL normale ;  
  
-   une fonction `DllMain` ou **RawDllMain** fournie dans une DLL normale ;  
  
-   une fonction `DllMain` ou **RawDllMain** fournie dans une DLL d'extension.  
  
 Pour plus d'informations sur la création de threads pendant l'initialisation, consultez l'article de la Base de connaissances \(en anglais\) « PRB: Cannot Create an MFC Thread During DLL Startup » \(Q142243\).  
  
## Voir aussi  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)
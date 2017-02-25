---
title: "Initialisation de DLL non-MFC | Microsoft Docs"
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
  - "DLL (C++), non MFC"
  - "initialiser les DLL"
  - "DLL non MFC (C++)"
ms.assetid: 2622b32a-28f9-4d61-9e46-6c19aaf8b7ad
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisation de DLL non-MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour initialiser des DLL non\-MFC, le code source de la DLL doit contenir une fonction appelée `DllMain`.  Le code suivant présente une structure de base qui donne une idée de ce que pourrait être la définition de `DllMain` :  
  
```  
BOOL APIENTRY DllMain(HANDLE hModule,   
                      DWORD  ul_reason_for_call,   
                      LPVOID lpReserved)  
{  
    switch( ul_reason_for_call ) {  
    case DLL_PROCESS_ATTACH:  
    ...  
    case DLL_THREAD_ATTACH:  
    ...  
    case DLL_THREAD_DETACH:  
    ...  
    case DLL_PROCESS_DETACH:  
    ...  
    }  
    return TRUE;  
}  
```  
  
> [!NOTE]
>  La documentation du [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] relative à **DllEntryPoint** indique que le nom réel de la fonction de point d'entrée doit être spécifié sur la ligne de commande de l'éditeur de liens à l'aide de l'option \/ENTRY.  Avec Visual C\+\+, il n'est pas nécessaire d'utiliser l'option \/ENTRY si le nom de la fonction de point d'entrée est `DllMain`.  En fait, si vous utilisez l'option \/ENTRY et donnez à la fonction de point d'entrée un nom autre que `DllMain`, la bibliothèque Runtime C ne sera pas initialisée correctement.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [\<caps:sentence id\="tgt7" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>La spécification de fonction pour DllMain \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Fonction de point d'entrée de bibliothèque de liens dynamiques \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
-   [Comportement de la bibliothèque Runtime C et DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
## Voir aussi  
 [Initialisation d'une DLL](../build/initializing-a-dll.md)
---
title: "Liaison explicite | Microsoft Docs"
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
  - "liaison explicite (C++)"
ms.assetid: 1e13d960-a195-4e6d-9864-7d8f3a701f4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Liaison explicite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec la liaison explicite, les applications doivent effectuer un appel de fonction pour charger explicitement la DLL au moment de l'exécution.  Pour établir une liaison explicite avec une DLL, une application doit :  
  
-   Appeler **LoadLibrary** \(ou une fonction similaire\) pour charger la DLL et obtenir un handle de module.  
  
-   Appeler **GetProcAddress** pour obtenir un pointeur de fonction désignant chaque fonction exportée que l'application souhaite appeler.  Comme les applications appellent les fonctions des DLL par l'intermédiaire d'un pointeur, le compilateur ne génère pas de références externes, et il n'est pas nécessaire d'établir une liaison avec une bibliothèque d'importation.  
  
-   Appeler **FreeLibrary** quand elle en a fini avec la DLL.  
  
 Par exemple :  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);         
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   [FreeLibrary et AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Voir aussi  
 [Liaison d'un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)
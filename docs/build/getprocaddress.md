---
title: "GetProcAddress | Microsoft Docs"
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
  - "GetProcAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), GetProcAddress"
  - "GetProcAddress (méthode)"
  - "exportations par ordinal (C++)"
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# GetProcAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les processus qui sont liés de manière explicite à une DLL appellent [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) pour obtenir l'adresse d'une fonction exportée de la DLL.  Vous utilisez le pointeur de fonction retourné pour appeler la fonction de la DLL.  **GetProcAddress** accepte comme paramètres le handle du module de la DLL \(retourné par **LoadLibrary**, `AfxLoadLibrary` ou **GetModuleHandle**\), et soit le nom de la fonction que vous souhaitez appeler soit l'ordinal d'exportation de la fonction.  
  
 Comme vous appelez la fonction de la DLL par l'intermédiaire d'un pointeur et qu'il n'y a pas de vérification de type au moment de la compilation, assurez\-vous que les paramètres de la fonction sont corrects de façon à éviter de dépasser la mémoire allouée sur la pile et de provoquer une violation d'accès.  L'une des façons d'assurer la sécurité des types est d'examiner les prototypes des fonctions exportées et de créer des typedefs correspondants pour les pointeurs de fonction.  Par exemple :  
  
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
  
 La manière dont vous spécifiez la fonction qui vous intéresse lorsque vous appelez **GetProcAddress** dépend du mode de génération de la DLL.  
  
 Vous pouvez obtenir l'ordinal d'exportation seulement si la DLL à laquelle vous vous liez a été générée à l'aide d'un fichier de définition de module \(.def\) et si les ordinaux sont listés avec les fonctions dans la section **EXPORTS** du fichier .def de la DLL.  L'appel à **GetProcAddress** à l'aide d'un ordinal d'exportation, de préférence au nom de fonction, est légèrement plus rapide si la DLL possède de nombreuses fonctions exportées car les ordinaux d'exportation servent d'index dans la table d'exportations de la DLL.  Avec un ordinal d'exportation, **GetProcAddress** peut localiser la fonction directement au lieu de comparer le nom spécifié aux noms des fonctions dans la table d'exportations de la DLL.  Cependant, vous devez appeler **GetProcAddress** à l'aide d'un ordinal d'exportation uniquement si vous avez le contrôle de l'assignation des ordinaux aux fonctions exportées dans le fichier .def.  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [\<caps:sentence id\="tgt17" sentenceid\="8c920606bb67e2587dd3c3e5cf977593" class\="tgtSentence"\>FreeLibrary\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Exportation à partir d'une DLL à l'aide de fichiers DEF](../build/exporting-from-a-dll-using-def-files.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)
---
title: "D&#233;chargement d&#39;une DLL &#224; chargement diff&#233;r&#233; | Microsoft Docs"
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
  - "__FUnloadDelayLoadedDLL2"
  - "chargement différé de DLL, déchargement"
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;chargement d&#39;une DLL &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'assistance de chargement différé fournie par défaut vérifie que les descripteurs de chargement différé ont un pointeur et une copie de la table des adresses d'importation \(IAT\) d'origine dans le champ pUnloadIAT.  Si c'est bien le cas, l'assistance enregistre un pointeur dans une liste dans le descripteur de différé des importations.  Cela permet à la fonction d'assistance de rechercher la DLL par son nom pour prendre en charge le déchargement explicite de cette DLL.  
  
 Voici les structures et fonctions associées permettant le déchargement explicite d'une DLL à chargement différé :  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 La structure UnloadInfo est implémentée à l'aide d'une classe C\+\+ qui utilise les implémentations de **LocalAlloc** et **LocalFree** respectivement comme ses opérateurs **new** et **delete**.  Ces options sont conservées dans une liste liée standard avec \_\_puiHead comme tête de liste.  
  
 L'appel de \_\_FUnloadDelayLoadedDLL résulte en une tentative de recherche du nom que vous fournissez dans la liste des DLL chargées \(une correspondance exacte est nécessaire\).  Si ce nom est trouvé, la copie de la table IAT dans pUnloadIAT est copiée sur la table IAT en cours d'exécution pour restaurer les pointeurs de thunk, la bibliothèque est libérée avec **FreeLibrary**, l'enregistrement **UnloadInfo** correspondant est détaché de la liste et supprimé et, enfin, la valeur TRUE est retournée.  
  
 L'argument de la fonction \_\_FUnloadDelayLoadedDLL2 respecte la casse.  Par exemple, vous spécifiez :  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 et non :  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## Voir aussi  
 [Understanding the Helper Function](http://msdn.microsoft.com/fr-fr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)
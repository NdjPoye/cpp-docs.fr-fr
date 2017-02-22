---
title: "D&#233;chargement explicite d&#39;une DLL &#224; chargement diff&#233;r&#233; | Microsoft Docs"
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
  - "/DELAY:UNLOAD (option de l'éditeur de liens)"
  - "__FUnloadDelayLoadedDLL2"
  - "DELAY:UNLOAD (option de l'éditeur de liens)"
  - "chargement différé de DLL, déchargement"
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# D&#233;chargement explicite d&#39;une DLL &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option de l'éditeur de liens [\/delay](../../build/reference/delay-delay-load-import-settings.md):unload vous permet de décharger une DLL à chargement différé.  Par défaut, lorsque votre code décharge la DLL \(avec \/delay:unload et **\_\_FUnloadDelayLoadedDLL2**\), les importations à chargement différé restent dans la table des adresses d'importation \(IAT, Import Address Table\).  Cependant, si vous utilisez \/delay:unload sur la ligne de commande de l'éditeur de liens, la fonction d'assistance prend en charge le déchargement explicite de la DLL, rétablissant la table des adresses d'importation à sa forme d'origine ; les pointeurs désormais non valides sont remplacés.  L'IAT est un champ dans [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) qui contient l'adresse d'une copie de l'IAT d'origine \(si elle existe\).  
  
## Exemple  
  
### Code  
  
```  
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD  
#include <windows.h>  
#include <delayimp.h>  
#include "MyDll.h"  
#include <stdio.h>  
  
#pragma comment(lib, "delayimp")  
#pragma comment(lib, "MyDll")  
int main()  
{  
    BOOL TestReturn;  
    // MyDLL.DLL will load at this point  
    fnMyDll();  
  
    //MyDLL.dll will unload at this point  
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");  
  
    if (TestReturn)  
        printf_s("\nDLL was unloaded");  
    else  
        printf_s("\nDLL was not unloaded");  
}  
```  
  
### Commentaires  
 Remarques importantes sur le déchargement d'une DLL à chargement différé :  
  
-   Vous pouvez trouver l'implémentation de la fonction **\_\_FUnloadDelayLoadedDLL2** dans le fichier \\VC7\\INCLUDE\\DELAYHLP.CPP.  
  
-   Le paramètre de nom de la fonction **\_\_FUnloadDelayLoadedDLL2** doit exactement correspondre \(avec respect de la casse\) au contenu de la bibliothèque d'importation \(cette chaîne se trouve également dans la table d'importation de l'image\).  Vous pouvez afficher le contenu de la bibliothèque d'importation avec [DUMPBIN \/DEPENDENTS](../../build/reference/dependents.md).  Si vous souhaitez une correspondance de chaînes ne respectant pas la casse, vous pouvez mettre à jour **\_\_FUnloadDelayLoadedDLL2** pour utiliser l'une des fonctions de chaîne CRT ou un appel API Windows.  
  
 Pour plus d'informations, consultez [Déchargement d'une DLL à chargement différé](../../build/reference/unloading-a-delay-loaded-dll.md).  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)
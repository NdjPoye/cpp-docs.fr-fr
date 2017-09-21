---
title: "Définitions et declarations (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e6523addc4ad4403c3dd74b5101081178b3ed2ec
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="definitions-and-declarations-c"></a>Définitions et déclarations (C)
**Section spécifique à Microsoft**  
  
 L'interface DLL fait référence à tous les éléments (fonctions et données) qui sont connus pour être exportés par un programme du système, c'est-à-dire tous les éléments déclarés comme **dllimport** ou `dllexport`. Toutes les déclarations incluses dans l'interface DLL doivent spécifier l'attribut **dllimport** ou `dllexport`. Toutefois, la définition peut spécifier uniquement l'attribut `dllexport`. Par exemple, la définition de fonction suivante génère une erreur de compilation :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int func()    /* Error; dllimport prohibited in */  
                        /* definition. */  
{  
   return 1;  
}  
```  
  
 Le code suivant génère aussi une erreur :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int i = 10;      /* Error; this is a definition. */  
```  
  
 Mais voici la syntaxe correcte :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport int i = 10;      /* Okay: this is an export definition. */  
```  
  
 L'utilisation de `dllexport` implique une définition tandis que **dllimport** implique une déclaration. Vous devez utiliser le mot clé `extern` avec `dllexport` pour forcer une déclaration. Sinon, une définition est impliquée.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k;   /* These are correct and imply */  
Dllimport int j;          /* a declaration. */      
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’importation et d’exportation de DLL](../c-language/dll-import-and-export-functions.md)
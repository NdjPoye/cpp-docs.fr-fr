---
title: "srand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "srand"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "srand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nombres, pseudo-aléatoire"
  - "nombres, aléatoire"
  - "nombres pseudo-aléatoires"
  - "nombres aléatoires, générer"
  - "point de départ aléatoire"
  - "point de départ aléatoire, définir"
  - "srand (fonction)"
  - "points de départ"
  - "points de départ, définir aléatoire"
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# srand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit la valeur de départ initiale pour le générateur de nombre pseudo\-aléatoire.  
  
## Syntaxe  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### Paramètres  
 `seed`  
 Valeur pour la génération de nombre pseudo\-aléatoire  
  
## Notes  
 La fonction `srand` définit le point de départ pour générer une série d'entiers pseudo\-aléatoires dans le thread actuel.  Pour réinitialiser le générateur pour créer la séquence de résultats, appelez la fonction `srand` et utilisez de nouveau le même argument `seed`.  Toute autre valeur pour `seed` définit le générateur à un point de départ différent dans la séquence pseudo\-aléatoire.  `rand` récupère les nombres pseudo\-aléatoires générés.  L'appel à `rand` avant tout appel à `srand` génère la même séquence qu'appeler `srand` avec `seed` passée comme 1.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`srand`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [rand](../../c-runtime-library/reference/rand.md).  
  
## Équivalent .NET Framework  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
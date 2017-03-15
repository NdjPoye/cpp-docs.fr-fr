---
title: "__max | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__max"
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
apitype: "DLLExport"
f1_keywords: 
  - "max"
  - "__max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__max (macro)"
  - "max (macro)"
  - "maximum (macro)"
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __max
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la plus grande des deux valeurs .  
  
## Syntaxe  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### Paramètres  
 `type`  
 Tous les types de données numériques  
  
 `a, b`  
 Valeurs de tout type numérique à comparer.  
  
## Valeur de retour  
 `__max` retourne la plus grande de ses arguments.  
  
## Notes  
 La macro `__max` compare deux valeurs et retourne la valeur la plus petite.  Les arguments peuvent être de n'importe quel type de données numérique, signé ou non signé.  Les arguments et la valeur de retour doivent être du même type de données.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`__max`|\<stdlib.h\>|  
  
## Exemple  
 Pour plus d'informations, consultez l'exemple fourni dans [\_min](../../c-runtime-library/reference/min.md).  
  
## Équivalent .NET Framework  
 [System::Math::Max](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_\_min](../../c-runtime-library/reference/min.md)
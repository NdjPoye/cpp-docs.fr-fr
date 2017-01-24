---
title: "Avertissement des outils &#201;diteur de liens LNK4217 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4217"
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole défini localement 'symbole' importé dans la fonction 'fonction'  
  
 [\_\_declspec\(dllimport\)](../../cpp/dllexport-dllimport.md) a été spécifié pour un symbole bien que ce symbole soit défini localement.  Supprimez le modificateur `__declspec` pour résoudre cet avertissement.  
  
 `symbol`  est le nom de symbole qui est défini dans l'image.  `function` est la fonction qui importe le symbole.  
  
 Cet avertissement n'apparaît pas lorsque vous compilez en utilisant l'option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L'avertissement LNK4217 peut également se produire si vous essayez de lier deux modules ensemble, alors que vous devriez plutôt compiler le deuxième module avec la bibliothèque d'importation du premier module.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Ensuite,  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 La tentative de liaison de ces deux modules entraîne l'avertissement LNK4217 ; pour le résoudre, compilez le deuxième exemple avec la bibliothèque d'importation du premier exemple.
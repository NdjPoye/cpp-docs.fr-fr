---
title: "Avertissement LNK4217 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4217
dev_langs: C++
helpviewer_keywords: LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09c984d7675c73bdf225bae7d3014f81153d20e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4217"></a>Avertissement des outils Éditeur de liens LNK4217
le symbole 'symbole' importé dans la fonction 'fonction' défini localement  
  
 [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) a été spécifié pour un symbole bien que le symbole est défini localement. Supprimer le `__declspec` modificateur pour résoudre cet avertissement.  
  
 `symbol`est le nom de symbole qui est défini dans l’image. `function`est la fonction qui importe le symbole.  
  
 Cet avertissement n’apparaît pas lorsque vous compilez à l’aide de l’option [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 LNK4217 peut également se produire si vous essayez de lier deux modules ensemble, lorsqu’à la place, vous devez compiler le deuxième module avec la bibliothèque d’importation du premier module.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Puis,  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Tentative de liaison de ces deux modules pour entraîner LNK4217, compilez le deuxième exemple avec la bibliothèque d’importation de l’exemple du premier pour résoudre.
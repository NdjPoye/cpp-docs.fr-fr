---
title: Compilateur avertissement (niveau 1) C4218 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4218
dev_langs: C++
helpviewer_keywords: C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 156a43f57f52f50f6542f3502658d5e0e16f1bd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4218"></a>Avertissement du compilateur (niveau 4) C4218
extension non standard utilisée : doit spécifier au moins une classe de stockage ou un type  
  
 Avec les extensions Microsoft (/Ze), vous pouvez déclarer une variable sans spécification d’une classe de stockage ou de type. Le type par défaut est `int`.  
  
## <a name="example"></a>Exemple  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 Ces déclarations sont non valides sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
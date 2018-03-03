---
title: Compilateur avertissement (niveau 1) C4744 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6fa95f8477f889aa8664d2b6d99c753cb9848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4744"></a>Avertissement du compilateur (niveau 1) C4744
'var' a un type différent dans 'fichier1' et 'fichier2' : 'type1' et 'type2'  
  
 Une variable externe référencée ou définie dans deux fichiers possède des types différents dans ces fichiers.  Pour résoudre, rendez les définitions de type, ou modifier le nom de variable dans un des fichiers.  
  
 C4744 est émise uniquement lorsque les fichiers sont compilés avec /GL.  Pour plus d’informations, consultez l’article [/GL (Optimisation de l’ensemble du programme)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  L’erreur C4744 se produit généralement dans les fichiers C (pas C++), car en C++, un nom de variable est décoré avec les informations de type.  Lors de l’échantillon (ci-dessous) est compile en C++, vous obtenez l’erreur de l’éditeur de liens LNK2019.  
  
## <a name="example"></a>Exemple  
 Cet exemple contient la première définition.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4744.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```
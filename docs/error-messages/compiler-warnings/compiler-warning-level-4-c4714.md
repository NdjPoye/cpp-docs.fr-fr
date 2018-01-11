---
title: Compilateur avertissement (niveau 4) C4714 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4714
dev_langs: C++
helpviewer_keywords: C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d49ff1bbf6538965d277b0afdd6c96fd9c71ef0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4714"></a>Avertissement du compilateur (niveau 4) C4714
' fonction ' marquée comme __forceinline non inline  
  
 La fonction donnée a été sélectionnée pour expansion inline, mais le compilateur n’a pas effectué l’incorporation (inlining).  
  
 Bien que `__forceinline` est une indication plus forte au compilateur que `__inline`, la fonctionnalité inline est toujours appliquée à la discrétion du compilateur, mais aucun heuristique n’est utilisées pour déterminer les avantages d’incorporation (inlining) cette fonction.  
  
 Dans certains cas, le compilateur n’incorpore pas une fonction particulière pour des raisons mécaniques. Par exemple, le compilateur n’incorpore pas :  
  
-   Une fonction si elle entraînerait le mélange SEH et C++ EH.  
  
-   Certaines fonctions de copie construit les objets passés par valeur lorsque - GX//EHs//EHa est activé.  
  
-   Des fonctions qui retournent un objet déroulable par valeur lorsque - GX//EHs//EHa est activé.  
  
-   Fonctions avec un assembly inline lors de la compilation sans - Og/Ox/O1/O2.  
  
-   Fonctions avec une liste d’arguments variable.  
  
-   Une fonction avec un **essayez** (des exceptions C++) instruction.  
  
 L’exemple suivant génère l’erreur C4714 :  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```
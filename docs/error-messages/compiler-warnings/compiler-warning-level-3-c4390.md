---
title: Compilateur avertissement (niveau 3) C4390 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4390
dev_langs: C++
helpviewer_keywords: C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d042a9d89ca30be5971f31360f7958e9fb96cf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4390"></a>Avertissement du compilateur (niveau 3) C4390
' ;' : vide instruction contrôlée a été trouvée. Cela est son but ?  
  
 Un point-virgule a été trouvé après une instruction de contrôle qui ne contient aucune instruction.  
  
 Si vous obtenez C4390 à cause d’une macro, vous devez utiliser le [avertissement](../../preprocessor/warning.md) pragma pour désactiver C4390 dans le module contenant la macro.  
  
 L’exemple suivant génère l’erreur C4390 :  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```
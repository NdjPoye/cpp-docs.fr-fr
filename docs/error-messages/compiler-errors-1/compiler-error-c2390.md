---
title: Erreur du compilateur C2390 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2390
dev_langs: C++
helpviewer_keywords: C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93d4cbd9de274d53fdc0369c2b85dbf2e97af48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2390"></a>Erreur du compilateur C2390
'identificateur' : classe de stockage incorrecte 'spécificateur'  
  
 La classe de stockage n’est pas valide pour l’identificateur de portée globale. La classe de stockage par défaut est utilisée à la place de la classe non valide.  
  
 Solutions possibles :  
  
-   Si l’identificateur est une fonction, déclarez-le avec `extern` stockage.  
  
-   Si l’identificateur est un paramètre formel ou une variable locale, déclarez-le avec stockage automatique.  
  
-   Si l’identificateur est une variable globale, déclarez-le sans classe de stockage (stockage automatique).  
  
## <a name="example"></a>Exemple  
  
-   L’exemple suivant génère l’erreur C2390 :  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```
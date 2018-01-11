---
title: Compilateur avertissement (niveau 2) C4285 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4285
dev_langs: C++
helpviewer_keywords: C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85f7904eb3a570b8f348503277117167a624a0d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4285"></a>Avertissement du compilateur (niveau 2) C4285
type de retour de 'identifier::operator ->' est récurrent si appliqué à l’aide de la notation infixe  
  
 Spécifié **operator -> ()** fonction ne peut pas retourner le type pour lequel elle est définie ou une référence au type pour lequel il est défini.  
  
 L’exemple suivant génère l’erreur C4285 :  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```
---
title: Compilateur avertissement (niveau 4) C4238 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4238
dev_langs: C++
helpviewer_keywords: C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>Avertissement du compilateur (niveau 4) C4238
extension non standard utilisée : classe rvalue utilisée comme lvalue  
  
 Pour la compatibilité avec les versions précédentes de Visual C++, les extensions Microsoft (**/Ze**) vous permettent d’utiliser un type de classe comme rvalue dans un contexte qui implicitement ou explicitement prend son adresse. Dans certains cas, par exemple, l’exemple ci-dessous, il peut s’avérer dangereux.  
  
## <a name="example"></a>Exemple  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Cette utilisation génère une erreur sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
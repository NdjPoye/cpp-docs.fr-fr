---
title: Compilateur avertissement (niveau 4) C4125 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4125
dev_langs: C++
helpviewer_keywords: C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6fbd012d11110e17d515021fcd8977ef4e6bd47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4125"></a>Avertissement du compilateur (niveau 4) C4125
un nombre décimal termine une séquence d’échappement octale  
  
 Le compilateur évalue le nombre octal sans le chiffre décimal et suppose que le chiffre décimal est un caractère.  
  
## <a name="example"></a>Exemple  
  
```  
// C4125a.cpp  
// compile with: /W4  
char array1[] = "\709"; // C4125  
int main()  
{  
}  
```  
  
 Si le chiffre 9 est censé être un caractère, corrigez l’exemple comme suit :  
  
```  
// C4125b.cpp  
// compile with: /W4  
char array[] = "\0709";  // C4125 String containing "89"  
int main()  
{  
}  
```
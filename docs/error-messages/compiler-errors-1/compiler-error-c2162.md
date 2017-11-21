---
title: Erreur du compilateur C2162 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2162
dev_langs: C++
helpviewer_keywords: C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 63c27d28a5c1546c65fe3df069482f9495d4f851
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2162"></a>Erreur du compilateur C2162
paramètre formel de macro attendu  
  
 Le jeton suivant un opérateur d’enchaînement (#) n’est pas un nom de paramètre formel.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2162 :  
  
```  
// C2162.cpp  
// compile with: /c  
#include <stdio.h>  
  
#define print(a) printf_s(b)   // OK  
#define print(a) printf_s(#b)    // C2162  
```
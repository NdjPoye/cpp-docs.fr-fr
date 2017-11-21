---
title: Erreur du compilateur C2861 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2861
dev_langs: C++
helpviewer_keywords: C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 18c51d01b8f273d4546f3411405fe511e31799ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2861"></a>Erreur du compilateur C2861
'nom de la fonction' : une fonction membre d’interface ne peut pas être définie.  
  
 Le compilateur a rencontré le mot clé interface ou déduit un struct en tant qu’interface mais puis trouvé un membre de la définition de fonction.  Une interface ne peut pas contenir une définition pour une fonction membre.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2861 :  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```
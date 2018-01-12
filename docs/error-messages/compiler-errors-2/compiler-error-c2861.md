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
ms.workload: cplusplus
ms.openlocfilehash: 927c1fb7e80da9d3a2dd221cb5bab3bb17abb109
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
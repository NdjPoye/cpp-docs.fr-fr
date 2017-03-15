---
title: "Erreur du compilateur C2861 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2861"
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nom de fonction' : impossible de définir une fonction membre d'interface  
  
 Le compilateur a rencontré le mot clé interface ou a déduit qu'un struct est une interface mais a ensuite trouvé une définition de fonction membre.  Une interface ne peut pas contenir de définition d'une fonction membre.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2861 :  
  
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
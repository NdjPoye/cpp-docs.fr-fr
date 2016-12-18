---
title: "Erreur du compilateur C3136 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3136"
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3136
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : une interface COM ne peut hériter que d'une autre interface COM, 'interface' n'est pas une interface COM  
  
 Une interface à laquelle vous avez appliqué un [attribut interface](../../windows/interface-attributes.md) hérite d'une interface qui n'est pas une interface COM.  Finalement, une interface COM hérite de `IUnknown`.  Toute interface précédée d'un attribut d'interface est une interface COM.  
  
 L'exemple suivant génère l'erreur C3136 :  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```
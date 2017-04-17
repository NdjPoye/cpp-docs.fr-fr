---
title: "C3353 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 051300b1c670381c0450b373058644fc5a84e7d4
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3353"></a>Erreur du compilateur C3353
'délégué' : un délégué ne peut être créé qu'à partir d'une fonction globale ou à partir d'une fonction membre d'un type managé ou WinRT  
  
 Délégués déclarés avec le [déléguer](../../windows/delegate-cpp-component-extensions.md) (mot clé), peut uniquement être déclaré dans une portée globale.  
  
 L'exemple suivant génère l'erreur C3353 :  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```
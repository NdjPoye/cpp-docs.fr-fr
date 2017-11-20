---
title: Erreur du compilateur C3247 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3247
dev_langs: C++
helpviewer_keywords: C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc07da3d6fa994bfba9588b1169287da8c0d738b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3247"></a>Erreur du compilateur C3247
'classe1' : une coclasse ne peut pas hériter d’une autre coclasse 'classe2'  
  
 Une classe marquée avec l’attribut [coclass](../../windows/coclass.md) ne peut pas hériter d’une classe marquée avec l’attribut `coclass` .  
  
 L’exemple suivant génère l’erreur C3247 :  
  
```  
// C3247.cpp  
[module(name="MyLib")];  
[coclass]  
class a {  
};  
  
[coclass]  
class b : public a {   // C3247  
};  
int main() {  
}  
```
---
title: "Erreur irrécupérable C1191 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1191
dev_langs: C++
helpviewer_keywords: C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95795ddfcc27a7cd150dec565f0e52a4f7eca00e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1191"></a>Erreur irrécupérable C1191
'dll' peut uniquement être importé dans une portée globale  
  
 L’instruction d’importation de mscorlib.dll dans un programme qui utilise la programmation /clr ne peut pas apparaître dans un espace de noms ou une fonction, mais il doit apparaître dans une portée globale.  
  
 L’exemple suivant génère l’erreur C1191 :  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Résolution possible :  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```
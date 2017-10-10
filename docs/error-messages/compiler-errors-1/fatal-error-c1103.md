---
title: "Erreur irrécupérable C1103 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 41759b75db078d4f689b12cc71d502ec907b56a2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1103"></a>Erreur irrécupérable C1103
erreur irrécupérable lors de l’importation de progid : 'message'  
  
 Le compilateur a détecté un problème d’importation d’une bibliothèque de types.  Par exemple, vous ne pouvez pas spécifier une bibliothèque de types avec progid et spécifier également `no_registry`.  
  
 Pour plus d’informations, consultez [Directive #import](../../preprocessor/hash-import-directive-cpp.md).  
  
 L’exemple suivant génère l’erreur C1103 :  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```

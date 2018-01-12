---
title: Erreur du compilateur C2460 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2460
dev_langs: C++
helpviewer_keywords: C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97ab5f3a2635bf25c01c2e54ba27c49447f1514a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2460"></a>Erreur du compilateur C2460
'identificateur1' : utilise 'identificateur2', qui est défini  
  
 Une classe ou structure (`identifier2`) est déclarée en tant que membre de lui-même (`identifier1`). Les définitions de classes et structures récursives ne sont pas autorisées.  
  
 L’exemple suivant génère l’erreur C2460 :  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 Au lieu de cela, utilisez une référence de pointeur de la classe.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```
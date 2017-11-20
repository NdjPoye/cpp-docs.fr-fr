---
title: Erreur du compilateur C2555 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2555
dev_langs: C++
helpviewer_keywords: C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64f66bf80e8e4b6ba7477691cb9675cec347807d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2555"></a>Erreur du compilateur C2555
'classe1::fonction1' : fonction virtuelle de substitution type de retour est différent et n’est pas covariant 'classe2::fonction2'  
  
 Une fonction virtuelle et une fonction de substitution dérivée ont des listes de paramètres sont identiques, mais différents types de retournés. Une fonction de substitution dans une classe dérivée ne peuvent pas différer d’une fonction virtuelle dans une classe de base uniquement par son type de retour.  
  
 Pour résoudre cette erreur, effectuez un cast de la valeur de retour après la fonction virtuelle a été appelé.  
  
 Vous pouvez également voir cette erreur si vous compilez avec/CLR.   Par exemple, Visual C++ équivalent à la déclaration c# suivante :  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Pour plus d’informations sur l’erreur C2555, consultez l’article Q240862 de la Base de connaissances Microsoft.  
  
 L’exemple suivant génère l’erreur C2555 :  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```
---
title: Erreur du compilateur C2884 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2884
dev_langs: C++
helpviewer_keywords: C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5916eeb4195d163cd698a9398fa411f56ad8610
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2884"></a>Erreur du compilateur C2884
'nom' : introduit par des conflits de déclaration using avec la fonction locale 'fonction'  
  
 Vous avez essayé de définir une fonction plusieurs fois. La première définition est une définition locale. La deuxième provient d’un espace de noms avec un `using` déclaration.  
  
 L’exemple suivant génère l’erreur C2884 :  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```
---
title: Erreur du compilateur C2870 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75b9189795c7351745e9624cfb9cc11259834b76
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2870"></a>Erreur du compilateur C2870
'nom' : une définition de l’espace de noms doit apparaître soit au niveau de la portée du fichier soit immédiatement au sein d’une autre définition de l’espace de noms  
  
 Vous avez défini l’espace de noms `name` incorrectement. Espaces de noms doit être définie dans la portée du fichier (à l’extérieur de tous les blocs et classes) ou immédiatement au sein d’un autre espace de noms.  
  
 L’exemple suivant génère l’erreur C2870 :  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```

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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: daf7a6d7598b8f341a2b1c413d8284ec6e56a3cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
---
title: Erreur du compilateur C2951 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad6d5f3b7ab97b799a23c124505d8930774918aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2951"></a>Erreur du compilateur C2951
déclarations de type sont uniquement autorisées au niveau de l’espace de noms global, ou portée de classe  
  
 Vous ne pouvez pas déclarer un générique ou la classe de modèle à l’extérieur global ou la portée espace de noms. Si vous apportez vos déclarations générique ou de modèle dans un fichier include, assurez-vous que le fichier include est dans une portée globale.  
  
 L’exemple suivant génère l’erreur C2951 :  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 L’erreur C2951 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```
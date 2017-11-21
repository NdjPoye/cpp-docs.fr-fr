---
title: Erreur du compilateur C2883 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2883
dev_langs: C++
helpviewer_keywords: C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 28c2031c3e659099507a8e59758e27f364dd29b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2883"></a>Erreur du compilateur C2883
'nom' : déclaration de fonction est en conflit avec 'identificateur' introduit par une déclaration using  
  
 Vous avez essayé de définir une fonction plusieurs fois. La première définition a été effectuée à partir d’un espace de noms avec un `using` déclaration. La deuxième était une définition locale.  
  
 L’exemple suivant génère l’erreur C2883 :  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```
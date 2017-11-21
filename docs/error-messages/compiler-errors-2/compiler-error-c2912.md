---
title: Erreur du compilateur C2912 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2912
dev_langs: C++
helpviewer_keywords: C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d19c1681274a03369987979af8c9c8a7253a5b57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2912"></a>Erreur du compilateur C2912
la spécialisation explicite 'déclaration' n'est pas une spécialisation d'un modèle de fonction  
  
 Vous ne pouvez pas spécialiser une fonction sans modèle.  
  
 L'exemple suivant génère l'erreur C2912 :  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 Cette erreur sera également générée suite à la mise en conformité du compilateur dans Visual Studio .NET 2003 : pour chaque spécialisation explicite, vous devez choisir les paramètres de la spécialisation explicite, de sorte qu'ils correspondent aux paramètres du modèle principal.  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```
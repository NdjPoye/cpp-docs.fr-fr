---
title: Erreur du compilateur C3269 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3269
dev_langs: C++
helpviewer_keywords: C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f1eb014e107326aa8c85b2439444c63525f26a77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3269"></a>Erreur du compilateur C3269
'fonction' : une fonction membre de géré ou WinRTtype ne peut pas être déclarée avec '...'  
  
Les fonctions membres de classe managée ou WinRT ne peuvent pas déclarer des listes de paramètres de longueur variable.  
  
L'exemple suivant génère l'erreur C3269 et montre comment la corriger :  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  

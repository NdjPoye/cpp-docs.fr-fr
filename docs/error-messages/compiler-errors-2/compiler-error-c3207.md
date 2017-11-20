---
title: Erreur du compilateur C3207 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3207
dev_langs: C++
helpviewer_keywords: C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d0f50d73f32a388669ea49af737b69b57d6a64d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3207"></a>Erreur du compilateur C3207
'fonction' : argument template non valide pour 'argument', modèle de classe attendu  
  
 Une fonction avec modèle est définie comme prenant un argument de type de modèle. Toutefois, un argument de type de modèle a été passé.  
  
 L’exemple suivant génère l’erreur C3207 :  
  
```  
// C3207.cpp  
template <template <class T> class TT>  
void f(){}  
  
template <class T>  
struct S  
{  
};  
  
void f1()  
{  
   f<S<int> >();   // C3207  
   // try the following line instead  
   // f<S>();  
}  
```
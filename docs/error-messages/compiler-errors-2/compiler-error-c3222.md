---
title: Erreur du compilateur C3222 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: bd1058f4e33bc70c9021bfb1ceff78af58d09552
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3222"></a>Erreur du compilateur C3222
’paramètre’ : impossible de déclarer des arguments par défaut pour des fonctions membres d’un type managé ou WinRT ou des fonctions génériques  
  
Il n’est pas autorisé de déclarer un paramètre de méthode avec un argument par défaut. Une forme surchargée de la méthode est une façon de contourner ce problème. Autrement dit, définissez une méthode portant le même nom sans paramètres, puis initialisez la variable dans le corps de la méthode.  
  
L'exemple suivant génère l'erreur C3222 :  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  


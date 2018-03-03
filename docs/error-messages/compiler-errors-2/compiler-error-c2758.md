---
title: Erreur du compilateur C2758 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a67a978883153e0de81e864bf01e8cf9ee2e13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2758"></a>Erreur du compilateur C2758
'membre' : un membre de type référence const doit être initialisé  
  
 L'erreur du compilateur C2758 survient quand le constructeur n'initialise pas un membre du type de référence dans une liste d'initialiseurs. Le compilateur laisse le membre non défini. Les variables du membre de référence doivent être initialisées quand elles sont déclarées ou se voir attribuer une valeur dans la liste d'initialisation du constructeur.  
  
 L'exemple suivant génère l'erreur C2758 :  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```
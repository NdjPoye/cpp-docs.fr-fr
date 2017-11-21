---
title: Erreur du compilateur C2909 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2909
dev_langs: C++
helpviewer_keywords: C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2163decefb2530a6a89b6db47e283878dd3abf7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2909"></a>Erreur du compilateur C2909
'identifier' : l’instanciation explicite d’un modèle de fonction exige un type de retour  
  
 Une instanciation explicite d’un modèle de fonction nécessite la spécification explicite de son type de retour. La spécification d’un type de retour implicite ne fonctionne pas.  
  
 L’exemple suivant génère l’erreur C2909 :  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```
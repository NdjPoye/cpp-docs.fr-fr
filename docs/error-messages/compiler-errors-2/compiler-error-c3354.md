---
title: Erreur du compilateur C3354 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3354
dev_langs:
- C++
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd5552afb4981a3ff5303f0f992dbea78cb3a36e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3354"></a>Erreur du compilateur C3354
'fonction' : la fonction utilisée pour créer un délégué ne peut pas avoir un type de retour 'type'  
  
 Les types suivants ne sont pas des types de retour valides pour un `delegate`:  
  
-   Pointeur vers fonction  
  
-   Pointeur vers membre  
  
-   Pointeur vers fonction membre  
  
-   Référence vers fonction  
  
-   Référence vers fonction membre  
  
 L’exemple suivant génère l’erreur C3354 :  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  

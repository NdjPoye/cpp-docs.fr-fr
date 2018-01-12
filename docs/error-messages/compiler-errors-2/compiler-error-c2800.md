---
title: Erreur du compilateur C2800 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2800
dev_langs: C++
helpviewer_keywords: C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f23c6a4d0a38b800db09125af2401237458a4fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2800"></a>Erreur du compilateur C2800
'operator opérateur' ne peut pas être surchargé.  
  
 Les opérateurs suivants ne peuvent pas être surchargés : accès au membre de classe (`.`), pointeur vers membre (`.*`), résolution de portée (`::`), expression conditionnelle (`? :`), et `sizeof`.  
  
 L’exemple suivant génère l’erreur C2800 :  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```
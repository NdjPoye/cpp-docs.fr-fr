---
title: "Du compilateur (niveau 1) d’avertissement C4042 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0801b3fb34b85a6b07127111b38a35ee826028c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4042"></a>Du compilateur (niveau 1) d’avertissement C4042
'identificateur' : classe de stockage incorrecte  
  
 La classe de stockage spécifié ne peut pas être utilisée avec cet identificateur dans ce contexte. Le compilateur utilise la classe de stockage par défaut à la place :  
  
-   `extern`, si *identificateur* est une fonction.  
  
-   **Auto**si *identificateur* est un paramètre formel ou une variable locale.  
  
-   Aucun stockage ne classe si *identificateur* est une variable globale.  
  
 Cet avertissement peut être provoqué par la spécification d’une classe de stockage autre que **inscrire** dans une déclaration de paramètre.  
  
 L’exemple suivant génère C4042  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```
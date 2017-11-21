---
title: "Du compilateur (niveau 1) d’avertissement C4042 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4042
dev_langs: C++
helpviewer_keywords: C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3369b2786c552e408e8eedf8e6ed8bf73f272ff6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
---
title: Erreur du compilateur C2530 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f9ea1b462f2e0b141bdc624d77f548f19c4b71a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2530"></a>Erreur du compilateur C2530
'identificateur' : les références doivent être initialisées  
  
 Vous devez initialiser une référence lorsqu’il a été déclaré, sauf si elle est déjà déclarée :  
  
-   Avec le mot clé [extern](../../cpp/using-extern-to-specify-linkage.md).  
  
-   En tant que membre d’une classe, structure ou union (et il est initialisé dans le constructeur).  
  
-   En tant que paramètre dans une définition ou déclaration de fonction.  
  
-   En tant que type de retour d’une fonction.  
  
 L’exemple suivant génère l’erreur C2530 :  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```
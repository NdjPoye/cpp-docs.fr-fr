---
title: Erreur du compilateur C2530 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2530
dev_langs: C++
helpviewer_keywords: C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9438937ad99e66d9e623e1e3703dc6496f8153a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
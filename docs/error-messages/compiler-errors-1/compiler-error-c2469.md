---
title: Erreur du compilateur C2469 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2469
dev_langs: C++
helpviewer_keywords: C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2eaaf49eca8dec7b34509b2c1533228962af9fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2469"></a>Erreur du compilateur C2469
'operator' : impossible d’allouer l’objet 'type'  
  
 Un type non valide a été passé à un opérateur.  
  
 L’exemple suivant génère l’erreur C2469 :  
  
```  
// C2469.cpp  
int main() {  
   int *i = new void;   // C2469  
   int *i = new int;   // OK  
}  
```
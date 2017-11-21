---
title: Erreur du compilateur C2971 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2971
dev_langs: C++
helpviewer_keywords: C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81194765278adc82d57a7a95cc8528f1fd6e1ef3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2971"></a>Erreur du compilateur C2971
'classe' : paramètre de modèle 'param' : 'arg' : une variable locale ne peut pas être utilisée comme argument sans type  
  
 Vous ne pouvez pas utiliser le nom ou l’adresse d’une variable locale comme argument de modèle.  
  
 L’exemple suivant génère l’erreur C2971 :  
  
```  
// C2971.cpp  
template <int *pi>   
class Y {};  
  
int global_var = 0;  
  
int main() {  
   int local_var = 0;  
   Y<&local_var> aY;   // C2971  
   // try the following line instead  
   // Y<&global_var> aY;  
}  
```
---
title: Erreur du compilateur C3893 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 49097d988175e7571c5825b4d54e1dd496fb2ba7
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3893"></a>Erreur du compilateur C3893
'var' : utilisation comme l-value des données membres initonly n’est autorisée uniquement dans un constructeur d’instance de la classe 'nom_type'  
  
 Statique [initonly](../../dotnet/initonly-cpp-cli.md) membres de données peuvent avoir uniquement leur adresse effectuée dans un constructeur statique.  
  
 Instance (non statique) les données membres initonly peuvent avoir uniquement leur adresse effectuée dans les constructeurs d’instance (non statique).  
  
 L’exemple suivant génère l’erreur C3893 :  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```

---
title: Erreur du compilateur C2274 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2274
dev_langs: C++
helpviewer_keywords: C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4315d1cfef9a0583b1f44c8caa264378e32f1a35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2274"></a>Erreur du compilateur C2274
'type' : non conforme à droite de '.' (opérateur)  
  
 Un type apparaît comme l’opérande de droite d’un opérateur d’accès aux membres (.).  
  
 Cette erreur peut être provoquée en essayant d’accéder à une conversion de type défini par l’utilisateur. Utilisez le mot clé `operator` entre la période et `type`.  
  
 L’exemple suivant génère l’erreur C2286 :  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```
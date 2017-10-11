---
title: Erreur du compilateur C2500 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b869ca0ba959e9b774a005298ef4456d0995156
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2500"></a>Erreur du compilateur C2500
'identificateur1' : 'identificateur2' est déjà une classe de base directe  
  
 Une classe ou une structure apparaît plusieurs fois dans une liste de classes de base.  
  
 Une base directe est celui mentionné dans la liste de base. Une base indirecte est une classe de base de l’une des classes dans la liste de base.  
  
 Une classe ne peut pas être spécifiée plusieurs fois en tant que classe de base directe. Une classe peut être utilisée comme classe de base indirecte plusieurs fois.  
  
 L’exemple suivant génère C2500 :  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```

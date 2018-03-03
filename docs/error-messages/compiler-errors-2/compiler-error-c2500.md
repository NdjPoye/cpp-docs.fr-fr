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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
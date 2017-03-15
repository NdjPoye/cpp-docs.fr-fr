---
title: "Erreur du compilateur C2500 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2500"
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2500
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur1' : 'identificateur2' est déjà une classe de base directe  
  
 Une classe ou une structure apparaît plusieurs fois dans une liste de classes de base.  
  
 Une base directe est une base mentionnée dans la liste de base.  Une base indirecte est une classe de base de l'une des classes de la liste de base.  
  
 Une classe ne peut pas être spécifiée comme classe de base directe plusieurs fois.  Elle peut servir de classe de base indirecte plusieurs fois.  
  
 L'exemple suivant génère l'erreur C2500 :  
  
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
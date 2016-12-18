---
title: "Erreur du compilateur C2243 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2243"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2243"
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2243
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La conversion 'type de conversion' de 'type1' en 'type2' existe, mais n'est pas accessible  
  
 La protection d'accès \(`protected` ou `private`\) a empêché la conversion d'un pointeur vers une classe dérivée en pointeur vers la classe de base.  
  
 L'exemple suivant génère l'erreur C2243 :  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 Les classes de base avec un accès `protected` ou `private` ne sont pas accessibles aux clients de la classe dérivée.  Ces niveaux de contrôle d'accès permettent d'indiquer que la classe de base est un détail d'implémentation qui doit être invisible pour les clients.  Utilisez une dérivation publique si vous souhaitez que les clients de la classe dérivée aient accès à une conversion implicite d'un pointeur de la classe dérivée en pointeur vers la classe de base.
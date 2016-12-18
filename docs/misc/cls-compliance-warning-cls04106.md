---
title: "Avertissement de conformit&#233; CLS CLS04106 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS04106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS04106"
ms.assetid: a74e4cb7-c96a-4673-bf11-c2ff3c4b02f1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233; CLS CLS04106
Les attributs doivent être de type 'System::Attribute' ou hériter de celui\-ci  
  
 Pour être conforme CLS, un attribut personnalisé doit hériter de System::Attribute.  Un attribut qui n’a pas hérité de System::Attribute a été appliqué à une fonction.  
  
 La déclaration suivante \(en langage d’assembly MSIL\) montre ce qui peut provoquer l’avertissement CLS04106 :  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Object  
```  
  
 puis une fonction qui utilise l’attribut :  
  
```  
.custom instance void MyAttribute::.ctor(int32) = ( 01 00 01 00 00 00 00 00 )  
```  
  
 Pour résoudre cet avertissement, faites dériver l’attribut de System::Attribute :  
  
```  
.class public auto ansi MyAttribute extends [mscorlib]System.Attribute  
```
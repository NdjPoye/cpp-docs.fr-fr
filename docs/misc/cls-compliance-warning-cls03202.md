---
title: "Avertissement de conformit&#233; CLS CLS03202 | Microsoft Docs"
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
  - "CLS03202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03202"
ms.assetid: 2219c86c-9276-4244-a2ff-bce578c4d65f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233; CLS CLS03202
Les méthodes add et remove d’un événement doivent chacune accepter un paramètre dont le type définit le type de l’événement et qui doit dériver de System.Delegate  
  
 Les méthodes add et remove d’un événement doivent chacune accepter un paramètre dont le type définit le type de l’événement et qui doit dériver de System.Delegate.  
  
 Pour plus d’informations sur la vérification de la conformité CLS, consultez [Assemblys conformes CLS](http://msdn.microsoft.com/fr-fr/3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 La déclaration de fonction suivante \(en langage d’assembly MSIL\) montre ce qui peut provoquer l’erreur CLS03202 :  
  
```  
// bad .method public specialname instance void add_MyEvent(class MyDelegate __unnamed000, int32 __extra) cil managed {}  
```  
  
 Vous pouvez résoudre cet avertissement si l’accesseur d’événement n’accepte qu’un seul paramètre :  
  
```  
.method public specialname instance void add_MyEvent(class MyDelegate __unnamed000) cil managed {}  
```
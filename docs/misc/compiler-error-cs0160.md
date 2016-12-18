---
title: "Erreur du compilateur CS0160 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0160"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0160"
ms.assetid: 4ef07061-8ef5-42d9-b043-3f81307d569f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Erreur du compilateur CS0160
Une clause catch précédente intercepte déjà toutes les exceptions de this ou d’un super type \('type'\)  
  
 Une série d’instructions **catch** doit être classée dans l’ordre décroissant de dérivation. Par exemple, les objets les plus dérivés doivent figurer en premier.  
  
 Pour plus d’informations, consultez [Instructions de gestion des exceptions](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) et [Exceptions et gestion des exceptions](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 L’exemple suivant génère l’avertissement CS0160 :  
  
```  
// CS0160.cs public class MyClass2 : System.Exception {} public class MyClass { public static void Main() { try {} catch(System.Exception) {}   // Second-most derived; should be second catch catch(MyClass2) {}   // CS0160  Most derived; should be first catch } }  
```
---
title: "Erreur du compilateur CS0199 | Microsoft Docs"
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
  - "CS0199"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0199"
ms.assetid: 9eede3f2-b55a-4b85-a05d-6bf177e1c602
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Erreur du compilateur CS0199
Les champs d’un champ readonly statique 'name' ne peuvent pas être passés en ref ou out \(sauf s’ils appartiennent à un constructeur statique\)  
  
 Une variable [readonly](../Topic/readonly%20\(C%23%20Reference\).md) doit avoir la même utilisation de [static](../Topic/static%20\(C%23%20Reference\).md) que le constructeur dans lequel vous voulez la passer en tant que paramètre [ref](../Topic/ref%20\(C%23%20Reference\).md) ou [out](../Topic/out%20\(C%23%20Reference\).md). Pour plus d’informations, consultez [Passage de paramètres](../Topic/Passing%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
## Exemple  
 L’exemple suivant génère l’erreur CS0199 :  
  
```  
// CS0199.cs class MyClass { public static readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // CS0199, TestInt is static } public static void Main() { } }  
```
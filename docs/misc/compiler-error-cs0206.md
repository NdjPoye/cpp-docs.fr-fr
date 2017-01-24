---
title: "Erreur du compilateur CS0206 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0206"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0206"
ms.assetid: d2f9838a-d8ae-4342-b8bd-fa5745619a26
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Erreur du compilateur CS0206
Impossible de passer une propriété ou un indexeur en tant que paramètre de sortie \(out\) ni de référence \(ref\)  
  
 Aucune [propriété](../Topic/Properties%20\(C%23%20Programming%20Guide\).md) n’est disponible pour être passée en tant que paramètre [ref](../Topic/ref%20\(C%23%20Reference\).md) ou [out](../Topic/out%20\(C%23%20Reference\).md). Pour plus d'informations, consultez [Passage de paramètres](../Topic/Passing%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
## Exemple  
 L’exemple suivant génère l’erreur CS0206 :  
  
```  
// CS0206.cs public class MyClass { public static int P { get { return 0; } set { } } public static void MyMeth(ref int i) // public static void MyMeth(int i) { } public static void Main() { MyMeth(ref P);   // CS0206 // try the following line instead // MyMeth(P);   // CS0206 } }  
```
---
title: "Avertissement de conformit&#233; CLS CLS01603 | Microsoft Docs"
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
  - "CLS01603"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01603"
ms.assetid: 608ff6e6-8669-4cc7-a85f-5b6915ee38d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233; CLS CLS01603
Les tableaux doivent avoir des éléments de type conforme CLS, et toutes les dimensions du tableau doivent avoir des limites inférieures égales à zéro  
  
 Les tableaux doivent avoir des éléments de type conforme CLS, et toutes les dimensions du tableau doivent avoir des limites inférieures égales à zéro. Seul le fait qu'un élément soit un tableau et le type d'élément du tableau seront requis pour distinguer les surcharges. Lorsque la surcharge est basée sur deux ou plusieurs types de tableau, les types d'élément seront des types nommés.  
  
 Pour plus d’informations sur la vérification de la conformité CLS, consultez [Assemblys conformes CLS](http://msdn.microsoft.com/fr-fr/3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 L’exemple suivant génère l’avertissement CLS01603 :  
  
```  
// CLS01603.cpp // compile with: /clr /LD // CLS01603 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(false)] public delegate void MyDelegate(Object ^ sender, EventArgs^ e); public delegate void MyDelegate2(Object ^ sender, EventArgs^ e); public ref struct One { array<MyDelegate^>^ MyArray;   // CLS01603 array<MyDelegate2^>^ MyArray2;   // OK };  
```
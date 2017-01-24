---
title: "Avertissement de conformit&#233; CLS CLS09911 | Microsoft Docs"
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
  - "CLS09911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS09911"
ms.assetid: 8cc0b0c0-a823-4392-9bf9-4d12242ef451
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Avertissement de conformit&#233; CLS CLS09911
Les types génériques ne sont pas conformes CLS  
  
 Un type conforme CLS ne peut pas être également un type générique.  Pour plus d’informations sur les génériques dans Visual C\+\+, consultez [Prise en charge des génériques en C\+\+](../windows/generics-cpp-component-extensions.md).  
  
 Pour plus d’informations sur la vérification de la conformité CLS \(Common Language Subset\), consultez [Assemblys conformes CLS](http://msdn.microsoft.com/fr-fr/3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 L’exemple suivant génère l’avertissement CLS09911 :  
  
```  
// CLS09911.cpp // compile with: /clr /LD using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; generic <class T> public ref class Five {   // CLS09911 };  
  
```
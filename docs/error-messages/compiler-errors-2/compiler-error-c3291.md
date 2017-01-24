---
title: "Erreur du compilateur C3291 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3291"
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'default' : ne peut pas être le nom d'une propriété triviale  
  
 Une propriété triviale ne peut pas être nommée `default`. Pour plus d'informations, voir [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3291.  
  
```  
// C3291.cpp // compile with: /clr /c ref struct C { property System::String ^ default;   // C3291 property System::String ^ Default;   // OK };  
```
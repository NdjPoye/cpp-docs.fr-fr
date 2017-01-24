---
title: "Erreur du compilateur C3296 | Microsoft Docs"
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
  - "C3296"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3296"
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3296
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property' : une propriété portant ce nom existe déjà  
  
 Le compilateur a rencontré plusieurs propriétés portant le même nom. Chaque propriété dans un type doit avoir un nom unique.  
  
 Pour plus d'informations, consultez [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3296.  
  
```  
// C3296.cpp // compile with: /clr /c using namespace System; ref class R { public: property int MyProp[int] { int get(int); } property String^ MyProp[int] { void set(int, String^); }   // C3296 };  
```
---
title: "Erreur du compilateur C3062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3062"
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum' : l'énumérateur requiert une valeur, car le type sous\-jacent est 'type'  
  
 Vous pouvez spécifier un type sous\-jacent pour une énumération.  Toutefois, certains types exigent que vous assigniez des valeurs à chaque énumérateur.  
  
 Pour plus d'informations sur les énumérateurs, consultez [Enum, classe](../../windows/enum-class-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3062 :  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```
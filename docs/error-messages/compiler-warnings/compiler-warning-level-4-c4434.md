---
title: "Avertissement du compilateur (niveau&#160;4) C4434 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4434"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4434"
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4434
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un constructeur de classe doit avoir un accès privé ; établissement d'un accès privé  
  
 L'erreur C4434 indique que le compilateur a modifié l'accessibilité d'un constructeur statique.  Les constructeurs static doivent avoir un accès privé, car ils sont uniquement destinés à être appelés par le Common Language Runtime.  Pour plus d'informations, consultez [Constructeurs statiques](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4434 :  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```
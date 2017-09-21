---
title: "Erreur du compilateur C3100 | Microsoft Docs"
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
  - "C3100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3100"
ms.assetid: 7a9c9eaf-08ef-442d-94a0-e457beee8549
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target' : qualificateur d'attribut inconnu  
  
 Une cible d'attribut non valide a été spécifiée.  
  
 Pour plus d'informations, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3100 :  
  
```  
// C3100.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::All)]  
public ref class Attr : public Attribute {  
public:  
   Attr(int t) : m_t(t) {}  
   int m_t;  
};  
  
[invalid_target:Attr(10)];   // C3100  
[assembly:Attr(10)];   // OK  
```
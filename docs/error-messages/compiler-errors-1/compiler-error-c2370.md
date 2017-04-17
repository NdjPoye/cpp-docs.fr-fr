---
title: "Erreur du compilateur C2370 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2370"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2370"
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2370
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : redéfinition ; classe de stockage différente  
  
 L’identificateur est déjà déclaré avec une autre classe de stockage.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2370 :  
  
```  
// C2370.cpp // compile with: /Za /c extern int i; static int i;   // C2370 int i;   // OK  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C2370 :  
  
```  
// C2370b.cpp #define Thread __declspec( thread ) extern int tls_i; int Thread tls_i;   // C2370 declaration and the definition differ int tls_i;   // OK  
```
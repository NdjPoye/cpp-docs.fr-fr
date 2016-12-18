---
title: "Erreur du compilateur&#160;C2004 | Microsoft Docs"
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
  - "C2004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2004"
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur&#160;C2004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

attendu 'defined\(id\)'  
  
 Un identificateur doit apparaître entre les parenthèses qui suivent le mot clé du préprocesseur.  
  
 Cette erreur peut également être générée en raison de la mise en conformité du compilateur pour Visual Studio .NET 2003 : parenthèses absentes dans la directive de préprocesseur. Si la parenthèse fermante est absente dans une directive de préprocesseur, le compilateur génère une erreur.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2004 :  
  
```  
// C2004.cpp // compile with: /DDEBUG #include <stdio.h> int main() { #if defined(DEBUG   // C2004 printf_s("DEBUG defined\n"); #endif }  
```  
  
## Exemple  
 Solution possible :  
  
```  
// C2004b.cpp // compile with: /DDEBUG #include <stdio.h> int main() { #if defined(DEBUG) printf_s("DEBUG defined\n"); #endif }  
```
---
title: "Erreur du compilateur C3275 | Microsoft Docs"
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
  - "C3275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3275"
ms.assetid: 5752680f-7d3e-4c42-ba9c-845e09d32e7a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum member' : impossible d’utiliser ce symbole sans qualificateur  
  
 Quand vous utilisez un code managé et que deux énumérations ou plus contiennent un identificateur ayant le même nom, vous devez explicitement qualifier les références à l’identificateur.  
  
 L’erreur C3275 ne peut être obtenue qu’avec **\/clr:oldSyntax**.  
  
 L’exemple suivant montre deux situations dans lesquelles l’erreur C3275 peut être générée :  
  
```  
// C3275.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __value enum Jewelry { necklace, brooch, pin, ring, earring }; __value enum Phone { busy, ring, disconnect }; int main() { Phone p = ring;   // C3275 // try the following line instead // Phone p = Phone::ring; Console::Out->Write(ring);   // C3275 // try the following line instead // Console::Out->Write(Phone::ring); }  
```
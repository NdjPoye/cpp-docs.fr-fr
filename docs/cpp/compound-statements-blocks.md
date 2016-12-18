---
title: "Instructions compos&#233;es (blocs) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "}"
  - "{"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "blocs, à propos des blocs"
  - "instructions composées"
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instructions compos&#233;es (blocs)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une instruction composée se compose de zéro, une ou plusieurs instructions entre accolades \(**{ }**\).  Une instruction composée peut être utilisée partout où une instruction est attendue.  Les instructions composées sont généralement appelées « blocs ».  
  
## Syntaxe  
  
```  
  
{ [ statement-list ] }  
```  
  
## Notes  
 L'exemple suivant utilise une instruction composée en tant que partie *statement* de l'instruction **if** \(consultez l'article [Instruction if](../cpp/if-else-statement-cpp.md) pour plus d'informations sur la syntaxe\) :  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
    Balance -= Amount;  
```  
  
> [!NOTE]
>  Comme une déclaration est une instruction, une déclaration peut être l'une des instructions figurant dans *statement\-list*.  Par conséquent, les noms déclarés au sein d'une instruction composée, mais pas explicitement déclarés comme statiques, ont une portée locale et \(pour les objets\) une durée de vie locale.  Consultez [Portée](../cpp/scope-visual-cpp.md) pour plus d'informations sur le traitement des noms avec une portée locale.  
  
## Voir aussi  
 [Vue d'ensemble des instructions C\+\+](../cpp/overview-of-cpp-statements.md)
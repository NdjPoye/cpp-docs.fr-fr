---
title: "COMM | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMM directive"
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# COMM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

crée une variable communale avec les attributs spécifiés dans `definition`.  
  
## Syntaxe  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## Notes  
 Chaque `definition` a la forme suivante :  
  
 \[*langtype*\[\] \[\] \[**PRÈS DE** &#124; *Nom***Numéro de téléphone :**`type`de**FAR**\] \[\] \[*nombre*de**Numéro de téléphone :**\]\]  
  
 *Le nom* correspond au nom de la variable.  `type` peut être tout spécificateur de type \([OCTET](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), etc.\) ou un entier spécifiant le nombre d'octets.  *Le nombre* spécifie le nombre d'objets de données \(il est la valeur par défaut\).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)
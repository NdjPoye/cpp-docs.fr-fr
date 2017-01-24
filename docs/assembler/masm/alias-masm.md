---
title: "ALIAS (MASM) | Microsoft Docs"
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
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ALIAS (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la directive d' **ALIAS** crée un autre nom pour une fonction.  Cela vous permet de créer plusieurs noms pour une fonction, ou créer des bibliothèques qui permettent à l'éditeur de liens \(LINK.exe\) pour mapper une fonction ancienne à une nouvelle fonction.  
  
## Syntaxe  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### Paramètres  
 `actual-name`  
 le nom réel de la fonction ou de la procédure.  Les crochets sont obligatoires.  
  
 `alias`  
 L'alias de remplacement ou.  Les crochets sont obligatoires.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)
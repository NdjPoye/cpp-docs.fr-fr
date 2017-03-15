---
title: "__wbinvd | Microsoft Docs"
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
  - "__wbinvd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wbinvd, intrinsèque"
  - "wbinvd, instruction"
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __wbinvd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère une ristourne et invalide l'instruction de cache \(`wbinvd`\).  
  
## Syntaxe  
  
```  
void __wbinvd(void);  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__wbinvd`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette fonction est uniquement disponible en mode noyau avec un niveau de privilège \(COMPLET\) de 0, et la routine est uniquement disponible sous forme intrinsèque.  
  
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)
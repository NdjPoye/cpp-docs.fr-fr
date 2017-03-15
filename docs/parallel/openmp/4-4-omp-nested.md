---
title: "4.4 OMP_NESTED | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.4 OMP_NESTED
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La variable d'environnement `OMP_NESTED` active ou désactive le parallélisme imbriqué à moins que le parallélisme imbriqué soit activé ou désactivé en appelant la routine de bibliothèque d' `o`**mp\_set\_nested** .  si l'ensemble à **TRUE**, parallélisme imbriqué est activé ; s'il est défini à **FALSE**, le parallélisme imbriqué est désactivé.  la valeur par défaut est **FALSE**.  
  
 Exemple :  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## renvoi :  
  
-   la fonction d'`omp_set_nested` , consultez [section 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) à la page 40.
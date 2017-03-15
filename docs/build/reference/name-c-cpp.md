---
title: "NAME (C/C++) | Microsoft Docs"
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
  - "name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAME (instruction de fichier .def)"
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NAME (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie le nom du fichier de sortie principal.  
  
```  
NAME [application][BASE=address]  
```  
  
## Notes  
 Vous pouvez spécifier un nom de fichier de sortie d'une manière équivalente à l'aide de l'option [\/OUT](../../build/reference/out-output-file-name.md) de l'éditeur de liens, et définir l'adresse de base d'une manière équivalente à l'aide de l'option [\/BASE](../../build/reference/base-base-address.md) de l'éditeur de liens.  Si les deux sont spécifiées, \/OUT substitue **NAME**.  
  
 Si vous générez une DLL, NAME affectera seulement le nom de la DLL.  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)
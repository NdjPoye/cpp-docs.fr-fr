---
title: "VERSION (C/C++) | Microsoft Docs"
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
  - "VERSION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VERSION (instruction de fichier .def)"
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VERSION (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

indique à LINK d'insérer un nombre dans l'en\-tête du fichier .exe ou de la DLL.  
  
```  
VERSION major[.minor]  
```  
  
## Notes  
 Les arguments *major* et *minor* sont des nombres décimaux compris entre 0 et 65 535.  La valeur par défaut correspond à la version 0.0.  
  
 Vous pouvez spécifier un numéro de version d'une manière équivalente à l'aide de l'option [Informations de version](../../build/reference/version-version-information.md) \(\/VERSION\).  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)
---
title: "LIBRARY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LIBRARY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIBRARY (instruction de fichier .def)"
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIBRARY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique à LINK de créer une DLL.  Parallèlement, LINK crée une bibliothèque d'importation, sauf si un fichier .exp est utilisé lors de la génération.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## Notes  
 L'argument *library* spécifie le nom de la DLL.  Vous pouvez également utiliser l'option [\/OUT](../../build/reference/out-output-file-name.md) de l'éditeur de liens pour spécifier le nom de sortie de la DLL.  
  
 L'argument BASE\=*adresse* définit l'adresse de base que le système d'exploitation utilise pour charger la DLL.  Cet argument substitue l'emplacement par défaut de la DLL 0x10000000.  Pour plus d'informations sur les adresses de base, consultez la description de l'option [\/BASE](../../build/reference/base-base-address.md).  
  
 Pensez à utiliser l'option [\/DLL](../../build/reference/dll-build-a-dll.md) de l'éditeur de liens quand vous générez une DLL.  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)
---
title: "STUB | Microsoft Docs"
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
  - "STUB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STUB (instruction de fichier .def)"
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# STUB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsqu'il est utilisé dans un fichier de définition de module qui génère un pilote de périphérique virtuel \(VxD\), STUB vous permet de spécifier un nom de fichier contenant une structure IMAGE\_DOS\_HEADER \(définie dans WINNT.H\) à utiliser dans le pilote de périphérique virtuel \(VxD\), à la place de l'en\-tête par défaut.  
  
```  
STUB:filename  
```  
  
## Notes  
 Vous pouvez spécifier l'argument *filename* de manière équivalente à l'aide de l'option [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) de l'éditeur de liens.  
  
 STUB est valide dans un fichier de définition de module uniquement lors de la génération d'un pilote VxD.  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)
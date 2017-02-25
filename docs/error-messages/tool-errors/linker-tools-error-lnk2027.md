---
title: "Erreur des outils &#201;diteur de liens LNK2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2027"
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur des outils &#201;diteur de liens LNK2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

référence de module non résolue 'module'  
  
 Un fichier passé à l'éditeur de liens possède une dépendance à un module qui n'était ni spécifié avec **\/ASSEMBLYMODULE**, ni passé directement à l'éditeur de liens.  
  
 Pour résoudre l'erreur LNK2027, effectuez l'une des opérations suivantes :  
  
-   Ne passez pas à l'éditeur de liens le fichier possédant la dépendance de module.  
  
-   Spécifiez le module avec **\/ASSEMBLYMODULE**.  
  
-   Si le module est un .netmodule sûr, passez le module directement à l'éditeur de liens.  
  
 Pour plus d’informations, consultez [\/ASSEMBLYMODULE \(Ajouter un module MSIL à l'assembly\)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) et [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).
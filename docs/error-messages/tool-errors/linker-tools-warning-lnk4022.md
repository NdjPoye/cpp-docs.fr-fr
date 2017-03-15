---
title: "Avertissement des outils &#201;diteur de liens LNK4022 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4022"
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de trouver une correspondance unique pour le symbole 'symbole'  
  
 LINK ou LIB a trouvé plusieurs correspondances du symbole non décoré donné et n'a pas pu résoudre l'ambiguïté.  Aucun fichier de sortie \(.exe, .dll, .exp ou .lib\) n'est produit.  Cet avertissement est suivi par un avertissement [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) pour chaque symbole dupliqué et est finalement suivi de l'erreur irrécupérable [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Pour éviter cet avertissement, spécifiez le symbole sous forme décorée.  Exécutez [DUMPBIN](../../build/reference/dumpbin-options.md) sur l'objet pour voir les noms décorés.
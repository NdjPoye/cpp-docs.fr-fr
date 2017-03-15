---
title: "Erreur BSCMAKE BK1514 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1514"
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur BSCMAKE BK1514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

tous les fichiers .SBR ont été tronqués, aucun trouvé dans nom\_fichier  
  
 Aucun des fichiers .sbr spécifiés pour une mise à jour ne faisait partie du fichier d'informations de consultation \(.bsc\) d'origine.  Pour trouver les noms des fichiers .sbr ayant causé cette erreur, lisez les avertissements [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) qui la précèdent.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Nom de fichier incorrect spécifié pour un fichier .sbr ou .bsc.  
  
2.  Fichier .bsc endommagé nécessitant BSCMAKE pour le régénérer.
---
title: "Avertissement NMAKE U4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4010"
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement NMAKE U4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cible' : échec de la génération ; \/K spécifié, suite ...  
  
 Une commande du bloc de commandes de la cible donnée a retourné un code de sortie autre que zéro.  L'option \/K a indiqué à NMAKE de poursuivre le traitement des parties non liées de la génération et d'émettre un code de sortie 1 quand la session NMAKE est terminée.  
  
 Si la cible donnée est elle\-même dépendante d'une autre cible, NMAKE émet un avertissement [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) après cet avertissement.
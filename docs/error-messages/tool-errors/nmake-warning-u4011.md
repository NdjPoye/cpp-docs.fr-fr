---
title: "Avertissement NMAKE U4011 | Microsoft Docs"
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
  - "U4011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4011"
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement NMAKE U4011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cible' : les dépendants ne sont pas tous disponibles ; cible non générée  
  
 Un dépendant de la cible donnée n'existait pas ou était obsolète, et une commande de mise à jour du dépendant a retourné un code de sortie autre que zéro.  L'option \/K a indiqué à NMAKE de poursuivre le traitement des parties non liées de la génération et d'émettre un code de sortie 1 quand la session NMAKE est terminée.  
  
 Cet avertissement est précédé par l'avertissement [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) pour chaque dépendant dont la création ou la mise à jour a échoué.
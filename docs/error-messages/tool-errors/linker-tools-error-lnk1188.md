---
title: "Erreur des outils &#201;diteur de liens LNK1188 | Microsoft Docs"
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
  - "LNK1188"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1188"
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1188
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BADFIXUPSECTION:: cible de correction non valide 'symbole' ; risque de section de longueur zéro  
  
 Lors de l'édition de liens d'un VxD, la cible d'un réadressage n'avait pas de section.  Avec LINK386 \(ancienne version\), un enregistrement OMF GROUP \(généré par une directive MASM GROUP\) peut avoir été utilisé pour associer la section de longueur nulle à une autre section de longueur non nulle.  Le format COFF ne prend pas en charge la directive GROUP ni les sections de longueur nulle.  Cette erreur peut survenir quand LINK convertit automatiquement ce type d'objet OMF au format COFF.
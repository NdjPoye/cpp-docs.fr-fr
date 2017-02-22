---
title: "Mise &#224; jour d&#39;une colonne quand une autre table contient une r&#233;f&#233;rence &#224; la ligne | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de lignes, mises à jour de colonnes"
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Mise &#224; jour d&#39;une colonne quand une autre table contient une r&#233;f&#233;rence &#224; la ligne
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Certains fournisseurs peuvent détecter les colonnes de la ligne qui sont modifiées, mais de nombreux fournisseurs ne le peuvent pas.  De ce fait, la mise à jour d'une colonne peut se traduire par une erreur quand il existe une référence à la ligne que vous essayez de mettre à jour.  Pour résoudre ce problème, créez un accesseur séparé contenant uniquement les colonnes que vous souhaitez modifier.  Passez le numéro de cet accesseur à `SetData`.  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)
---
title: "Coupure des mots dans les contr&#244;les RichEdit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coupure des mots dans CRichEditCtrl"
  - "CRichEditCtrl (classe), coupure des mots dans"
  - "contrôles RichEdit, coupure des mots dans"
  - "coupure des mots"
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Coupure des mots dans les contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) appelle une fonction appelée « une procédure de saut de mot » pour rechercher des sauts entre les mots et déterminer où il pourra des lignes de changement.  La commande utilise ces informations d'effectuer des opérations de retour automatique à la ligne et en traitant les combinaisons de touches de CTRL\+LEFT et de CTRL\+RIGHT.  Une application peut envoyer des messages à un contrôle RichEdit pour remplacer la procédure par défaut de division des mots, pour extraire les informations de division des mots, et pour déterminer sur quelle ligne tombe un caractère donné.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)
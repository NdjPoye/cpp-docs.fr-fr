---
title: "TN047&#160;: assouplissement des sp&#233;cifications relatives aux transactions de base de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN047"
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN047&#160;: assouplissement des sp&#233;cifications relatives aux transactions de base de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque technologique, qui présentait les spécifications de transaction des classes de base de données ODBC MFC, est désormais obsolète.  Avant MFC 4.2, les classes de base de données requerraient que les curseurs soient conservés sur les jeux d'enregistrement après une opération **CommitTrans** ou **Restaurer**.  Si le pilote ODBC et le SGBD ne prenait pas en charge ce niveau de la rétention de curseur, les classes de base de données ne permettaient pas les transactions.  
  
 À compter de MFC 4.2, les classes de base de données ont levé la restriction de recourir à la conservation de curseur.  Les transactions sont activées si le pilotes les supporte.  Toutefois, vous devez maintenant activer le résultat d'une opération **CommitTrans** ou **Rollback** sur les jeux d'enregistrement ouverts.  Consultez les fonctions membres [CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md) et [CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md) pour plus d'informations.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
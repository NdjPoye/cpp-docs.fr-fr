---
title: "R&#233;cup&#233;rer des donn&#233;es d&#39;un objet Dialog | Microsoft Docs"
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
  - "capturer l'entrée d'utilisateur"
  - "données (MFC), boîtes de dialogue"
  - "données (MFC), récupérer"
  - "récupération des données (C++), boîtes de dialogue"
  - "DDX (échange de données de boîtes de dialogue) (C++)"
  - "DDX (échange de données de boîtes de dialogue) (C++), à propos de DDX"
  - "DDX (échange de données de boîtes de dialogue) (C++), récupérer des données d'un objet Dialog"
  - "contrôles de boîte de dialogue (C++), initialiser des valeurs"
  - "données de boîte de dialogue (C++)"
  - "données de boîte de dialogue (C++), récupérer"
  - "boîtes de dialogue (C++), récupérer les données utilisateur"
  - "GetDlgItemText (méthode)"
  - "GetWindowText (méthode)"
  - "boîtes de dialogue MFC, récupérer l'entrée d'utilisateur"
  - "récupérer des données"
  - "SetDlgItemText (méthode)"
  - "SetWindowText (méthode)"
  - "entrée d'utilisateur (C++), récupérer à partir de boîtes de dialogues MFC"
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# R&#233;cup&#233;rer des donn&#233;es d&#39;un objet Dialog
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'infrastructure fournit un moyen facile d'initialiser les valeurs de contrôles dans une boîte de dialogue et de récupérer les valeurs des contrôles.  L'approche manuelle plus laborieuse consiste à appeler des fonctions telles que les fonctions membres `SetDlgItemText` et `GetDlgItemText` de la classe `CWnd`, qui s'appliquent aux fenêtres de contrôle.  Avec ces fonctions, vous accédez à chaque contrôle individuellement pour définir ou pour obtenir la valeur, en appelant des fonctions comme `SetWindowText` et `GetWindowText`.  L'approche de l'infrastructure automatise l'initialisation et la récupération.  
  
 L'échange de données de boîtes de dialogue \(DDX\) permet d'échanger des données entre les contrôles dans la boîte de dialogue et les variables membres de l'objet du dialogue plus facilement.  L'échange se fait dans les deux sens.  Pour initialiser les contrôles dans la boîte de dialogue, vous pouvez définir les valeurs des données membres dans l'objet du dialogue, et l'infrastructure transfèrera les valeurs aux contrôles avant que la boîte de dialogue s'affiche.  Vous pouvez à tout moment mettre à jour les données de dialogue membres avec des données entrées par l'utilisateur.  À ce stade, vous pouvez utiliser les données en faisant référence aux variables de données membres.  
  
 Vous pouvez également faire en sorte que les valeurs de contrôle de la boîte de dialogue soient validées automatiquement à la validation des données de dialogue\(DDV\).  
  
 DDX et DDV sont expliquées plus en détail dans [Échange de données de boîtes de dialogue et validation](../mfc/dialog-data-exchange-and-validation.md).  
  
 Pour une boîte de dialogue modale, vous pouvez récupérer toutes les données entrées par l'utilisateur lorsque `DoModal` retourne **IDOK** mais avant que l'objet DIALOG soit détruit.  Pour une boîte de dialogue non modale, vous pouvez récupérer des données de l'objet de dialogue à tout moment en appelant `UpdateData` avec l'argument **TRUE** puis en accédant aux variables membres de la classe de la boîte de dialogue.  Cette rubrique est présenté plus en détail dans [Échange de données de boîtes de dialogue et validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)
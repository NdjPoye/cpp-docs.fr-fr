---
title: "&#201;change des donn&#233;es | Microsoft Docs"
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
  - "DDX (échange de données de boîtes de dialogue), feuilles de propriétés"
  - "échanger des données avec des feuilles de propriétés"
  - "feuilles de propriétés, échange de données"
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;change des donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme avec la plupart des boîtes de dialogue, l'échange de données entre la feuille de propriétés et des applications représentent l'une des fonctions les plus importantes de la feuille de propriétés.  Cet article explique comment accomplir cette tâche.  
  
 Échange de données avec une feuille de propriétés est en réalité une question d'échange de données avec des pages de propriétés de la feuille de propriétés.  La procédure pour échanger des données avec une page de propriétés est la même que pour l'échange de données avec une boîte de dialogue, car un objet [CPropertyPage](../mfc/reference/cpropertypage-class.md) est simplement un objet spécial [CDialog](../mfc/reference/cdialog-class.md).  La procédure bénéficie de la fonction de l'échange de données de boîtes de dialogue de l'infrastructure \(DDX\), les données d'échanges entre des contrôles dans une boîte de dialogue et les variables membres de la boîte de dialogue objet.  
  
 La différence importante entre l'échange de données avec une feuille de propriétés et une boîte de dialogue standard est que la feuille de propriétés contient plusieurs pages, vous devez les données d'échange avec toutes les pages dans la feuille de propriétés.  Pour plus d'informations sur DDX, consultez [Échange et validation de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md).  
  
 L'exemple suivant illustre échanger des données entre une vue et deux pages d'une feuille de propriétés :  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/CPP/exchanging-data_1.cpp)]  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)
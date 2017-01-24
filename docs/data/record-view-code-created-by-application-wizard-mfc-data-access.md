---
title: "Code de vue de l&#39;enregistrement cr&#233;&#233; par l&#39;Assistant Application (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "Assistants Application (C++), code de vue d'enregistrement"
  - "vues des enregistrements, Assistant Application (code)"
  - "vues des enregistrements, actualiser des contrôles"
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Code de vue de l&#39;enregistrement cr&#233;&#233; par l&#39;Assistant Application (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'[Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md) remplace les fonctions membres `OnInitialUpdate` et `OnGetRecordset` de la vue.  Une fois que l'infrastructure a créé la fenêtre frame, le document et la vue, elle appelle `OnInitialUpdate` pour initialiser la vue.  `OnInitialUpdate` obtient un pointeur vers le recordset à partir du document.  Un appel à la fonction [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) de la classe de base ouvre le recordset.  Le code suivant illustre ce processus pour un `CRecordView` : le code pour un `CDaoRecordView` est similaire :  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 Quand le recordset s'ouvre, il sélectionne des enregistrements.  [CRecordset::Open](../Topic/CRecordset::Open.md) ou [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) fait du premier enregistrement l'enregistrement actif et DDX déplace les données à partir des données membres de champ du recordset vers les contrôles de formulaire correspondants dans la vue.  Pour plus d'informations sur RFX, consultez [Record Field Exchange \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  Pour plus d'informations sur DDX, consultez [Échange et validation de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md).  Pour plus d'informations sur le processus de création de document\/vue, consultez [Utilisation des classes pour l'écriture d'applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
> [!NOTE]
>  Vous devez laisser à vos utilisateurs finaux la possibilité d'actualiser les contrôles de vue d'enregistrement à partir du recordset.  Sans cette fonctionnalité, si un utilisateur affecte à un contrôle une valeur non valide, il risque de rester de manière permanente sur l'enregistrement actif.  Pour actualiser les contrôles, vous devez appeler la fonction membre `CWnd` [UpdateData](../Topic/CWnd::UpdateData.md) avec un paramètre **FALSE**.  
  
## Voir aussi  
 [Utilisation d'une vue de l'enregistrement](../data/using-a-record-view-mfc-data-access.md)
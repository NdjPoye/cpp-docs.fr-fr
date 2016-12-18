---
title: "CRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordView (classe)"
  - "ODBC (recordsets), viewing records"
  - "enregistrements, viewing ODBC"
  - "vues, ODBC"
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordView::CRecordView](../Topic/CRecordView::CRecordView.md)|Construit un objet `CRecordView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordView::IsOnFirstRecord](../Topic/CRecordView::IsOnFirstRecord.md)|Retourne une valeur différente de zéro si l'enregistrement en cours est le premier enregistrement du recordset associé.|  
|[CRecordView::IsOnLastRecord](../Topic/CRecordView::IsOnLastRecord.md)|Retourne une valeur différente de zéro si l'enregistrement en cours est le dernier enregistrement du recordset associé.|  
|[CRecordView::OnGetRecordset](../Topic/CRecordView::OnGetRecordset.md)|Retourne un pointeur vers un objet d'une classe dérivée d' `CRecordset`.  Assistant classe substitue cette fonction pour vous et crée le recordset si nécessaire.|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)||  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)|Si l'enregistrement en cours a changé, le met à jour dans la source de données, puis passe à l'enregistrement spécifié \(ensuite, précédent, premier, ou dernier\).|  
  
## Notes  
 La vue est une vue de type formulaire directement connectée à un objet d' `CRecordset` .  La vue est créée pour une ressource modèle de boîte de dialogue et affiche les champs de l'objet d' `CRecordset` dans les contrôles du modèle de boîte de dialogue.  L'objet d' `CRecordView` utilise l'échange de données de boîtes de dialogue \(DDX\) et l'record field exchange \(bulk RFX\) pour automatiser le déplacement des données entre les contrôles du formulaire et les champs du recordset.  `CRecordView` fournit également une implémentation par défaut pour passer au premier, ensuite, précédent, ou dernier enregistrement et une interface pour mettre à jour l'enregistrement actuellement dans la vue.  
  
> [!NOTE]
>  Si vous utilisez DAO \(DAO\) classe plutôt que les classes ODBC \(Open Database Connectivity\), utilisez la classe [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) à la place.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 La méthode la plus courante pour créer la vue de l'enregistrement est à l'aide de l'Assistant Application.  Tge Assistant Application crée la classe d'affichage de l'enregistrement et sa classe de recordset associée dans le cadre de votre application squelette de démarrage.  Si vous ne créez pas la classe d'affichage des enregistrements à l'aide de l'Assistant Application, vous pouvez le créer ultérieurement avec assistant classe.  Si vous avez besoin uniquement d'un formulaire unique, l'approche de l'Assistant Application est plus facile.  Assistant classe vous permet de choisir d'utiliser une vue de l'enregistrement ultérieurement dans le processus de développement.  L'assistant classe créer une vue de l'enregistrement et un recordset séparément et les connecter ensuite est l'approche la plus flexible car elle vous offre plus de contrôle en nommant la classe de recordset et son. fichiers de H\/.CPP.  Cette approche vous permet également d'avoir plusieurs vues des enregistrements dans la même classe de recordset.  
  
 Pour rendre facile pour les utilisateurs de passer d'un enregistrement à l'autre dans la vue de l'enregistrement, l'Assistant Application crée des ressources de menu \(et éventuellement barre d'outils\) pour l'enregistrement déplaçant le premier, ensuite, précédent, ou dernier.  Si vous créez une classe d'affichage de l'enregistrement avec assistant classe, vous devez créer ces ressources vous\-même dans le menu et éditeurs de bitmaps.  
  
 Pour plus d'informations sur l'implémentation par défaut pour passer d'un enregistrement à l'autre, consultez l' `IsOnFirstRecord` et `IsOnLastRecord` et l'article [Utilisation d'une vue de l'enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView` contient la position de l'utilisateur dans le recordset afin que la vue de l'enregistrement puisse mettre à jour l'interface utilisateur.  Lorsque l'utilisateur passe à l'un ou l'autre de fin du recordset, la vue de l'enregistrement désactive les objets interface utilisateur \(tels que les éléments de menu ou des boutons de barre d'outils \)pour déplacer plus loin dans la même direction.  
  
 Pour plus d'informations sur déclarer et utiliser la vue de l'enregistrement et classes de recordset, consultez « concevoir et créer une vue de l'enregistrement » dans l'article [vues des enregistrements](../../data/record-views-mfc-data-access.md).  Pour plus d'informations sur la façon dont les vues des enregistrements fonctionnent et comment les utiliser, consultez l'article [Utilisation d'une vue de l'enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)
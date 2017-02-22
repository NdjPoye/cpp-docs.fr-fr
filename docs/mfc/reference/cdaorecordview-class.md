---
title: "CDaoRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistants Application (C++), creating record views"
  - "contrôles dépendants (C++), displaying database data"
  - "CDaoRecordView (classe)"
  - "controls [MFC], liaison de données"
  - "liaison de données (C++), DAO views"
  - "contrôles liés aux données (C++), contrôles DAO"
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## Syntaxe  
  
```  
  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoRecordView::CDaoRecordView](../Topic/CDaoRecordView::CDaoRecordView.md)|Construit un objet `CDaoRecordView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](../Topic/CDaoRecordView::IsOnFirstRecord.md)|Retourne une valeur différente de zéro si l'enregistrement en cours est le premier enregistrement du recordset associé.|  
|[CDaoRecordView::IsOnLastRecord](../Topic/CDaoRecordView::IsOnLastRecord.md)|Retourne une valeur différente de zéro si l'enregistrement en cours est le dernier enregistrement du recordset associé.|  
|[CDaoRecordView::OnGetRecordset](../Topic/CDaoRecordView::OnGetRecordset.md)|Retourne un pointeur vers un objet d'une classe dérivée d' `CDaoRecordset`.  Assistant classe substitue cette fonction pour vous et crée le recordset si nécessaire.|  
|[CDaoRecordView::OnMove](../Topic/CDaoRecordView::OnMove.md)|Si l'enregistrement en cours a changé, le met à jour dans la source de données, puis passe à l'enregistrement spécifié \(ensuite, précédent, premier, ou dernier\).|  
  
## Notes  
 La vue est une vue de type formulaire directement connectée à un objet d' `CDaoRecordset` .  La vue est créée pour une ressource modèle de boîte de dialogue et affiche les champs de l'objet d' `CDaoRecordset` dans les contrôles du modèle de boîte de dialogue.  L'objet d' `CDaoRecordView` utilise l'échange de données de boîtes de dialogue \(DDX\) et le processus DFX \(DFX\) pour automatiser le déplacement des données entre les contrôles du formulaire et les champs du recordset.  `CDaoRecordView` fournit également une implémentation par défaut pour passer au premier, ensuite, précédent, ou dernier enregistrement et une interface pour mettre à jour l'enregistrement actuel en mode.  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO ; les classes DAO offrent généralement des fonctionnalités améliorées car elles utilisent le moteur de base de données Microsoft Jet.  
  
 La méthode la plus courante pour créer la vue de l'enregistrement est à l'aide de l'Assistant Application.  L'Assistant Application crée la classe d'affichage de l'enregistrement et sa classe de recordset associée dans le cadre de votre application squelette de démarrage.  
  
 Si vous avez besoin uniquement d'un formulaire unique, l'approche de l'Assistant Application est plus facile.  Assistant classe vous permet de choisir d'utiliser une vue de l'enregistrement ultérieurement dans le processus de développement.  Si vous ne créez pas la classe d'affichage des enregistrements à l'aide de l'Assistant Application, vous pouvez le créer ultérieurement avec assistant classe.  L'assistant classe créer une vue de l'enregistrement et un recordset séparément et les connecter ensuite est l'approche la plus flexible car elle vous offre plus de contrôle en nommant la classe de recordset et son. fichiers de H\/.CPP.  Cette approche vous permet également d'avoir plusieurs vues des enregistrements dans la même classe de recordset.  
  
 Pour rendre facile pour les utilisateurs de passer d'un enregistrement à l'autre dans la vue de l'enregistrement, l'Assistant Application crée des ressources de menu \(et éventuellement barre d'outils\) pour l'enregistrement déplaçant le premier, ensuite, précédent, ou dernier.  Si vous créez une classe d'affichage de l'enregistrement avec assistant classe, vous devez créer ces ressources vous\-même dans le menu et éditeurs de bitmaps.  
  
 Pour plus d'informations sur l'implémentation par défaut pour passer d'un enregistrement à l'autre, consultez `IsOnFirstRecord` et `IsOnLastRecord` et l'article [Utilisation d'une vue de l'enregistrement](../../data/using-a-record-view-mfc-data-access.md), qui s'applique à `CRecordView` et à `CDaoRecordView`.  
  
 `CDaoRecordView` contient la position de l'utilisateur dans le recordset afin que la vue de l'enregistrement puisse mettre à jour l'interface utilisateur.  Lorsque l'utilisateur passe à l'un ou l'autre de fin du recordset, la vue de l'enregistrement désactive les objets interface utilisateur \(tels que les éléments de menu ou des boutons de barre d'outils \)pour déplacer plus loin dans la même direction.  
  
 Pour plus d'informations sur déclarer et utiliser la vue de l'enregistrement et classes de recordset, consultez « concevoir et créer une vue de l'enregistrement » dans l'article [vues des enregistrements](../../data/record-views-mfc-data-access.md).  Pour plus d'informations sur la façon dont les vues des enregistrements fonctionnent et comment les utiliser, consultez l'article [Utilisation d'une vue de l'enregistrement](../../data/using-a-record-view-mfc-data-access.md).  Tous les éléments mentionnés ci\-dessus s'appliquent à `CRecordView` et à `CDaoRecordView`.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)
---
title: "COleDBRecordView Class | Microsoft Docs"
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
  - "COleDBRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView (classe)"
  - "MFC, OLE DB"
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDBRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## Syntaxe  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDBRecordView::COleDBRecordView](../Topic/COleDBRecordView::COleDBRecordView.md)|Construit un objet `COleDBRecordView`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDBRecordView::OnGetRowset](../Topic/COleDBRecordView::OnGetRowset.md)|Retourne une valeur standard d' `HRESULT` .|  
|[COleDBRecordView::OnMove](../Topic/COleDBRecordView::OnMove.md)|Place l'enregistrement courant \(si modifié\) dans la source de données puis passe à jour de l'enregistrement spécifié \(ensuite, précédent, premier, ou dernier\).|  
  
## Notes  
 La vue est une vue de type formulaire directement connectée à un objet d' `CRowset` .  La vue est créée pour une ressource modèle de boîte de dialogue et affiche les champs de l'objet d' `CRowset` dans les contrôles du modèle de boîte de dialogue.  L'objet d' `COleDBRecordView` utilise l'échange de données de boîtes de dialogue \(DDX\), et les fonctionnalités de navigation intégrée dans `CRowset`, pour automatiser le déplacement des données entre les contrôles du formulaire et les champs du jeu de lignes.  `COleDBRecordView` fournit également une implémentation par défaut pour passer au premier, ensuite, précédent, ou dernier enregistrement et une interface pour mettre à jour l'enregistrement actuellement dans la vue.  
  
 Vous pouvez utiliser des fonctions DDX avec **COleDbRecordView** pour obtenir des données directement du recordset de la base de données et les afficher dans un contrôle de boîte de dialogue.  Vous devez utiliser les méthodes **DDX\_\*** \(telles que `DDX_Text`\), mais pas les fonctions **DDX\_Field\*** \(telles que `DDX_FieldText`\) avec **COleDbRecordView**.  `DDX_FieldText` ne fonctionnera pas avec **COleDbRecordView** car `DDX_FieldText` prend un argument de type **CRecordset\*** \(pour `CRecordView`\) ou **CDaoRecordset\*** \(pour `CDaoRecordView`\).  
  
> [!NOTE]
>  Si vous utilisez DAO \(DAO\) classe plutôt que les classes de modèles du consommateur OLE DB, utilisez la classe [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) à la place.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView` contient la position de l'utilisateur dans le jeu de lignes afin que la vue de l'enregistrement puisse mettre à jour l'interface utilisateur.  Lorsque l'utilisateur passe à l'un ou l'autre de fin du jeu de lignes, la vue de l'enregistrement désactive les objets interface utilisateur \(tels que les éléments de menu ou des boutons de barre d'outils \)pour déplacer plus loin dans la même direction.  
  
 Pour plus d'informations sur les classes rowset, consultez l'article de [Utilisation des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## Configuration requise  
 **Header:** afxoledb.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
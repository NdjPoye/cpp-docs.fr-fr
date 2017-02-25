---
title: "CDragListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDragListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDragListBox class"
  - "drag list box [C++]"
  - "dragging list items"
  - "zones de liste"
  - "Windows (C++), zones de liste"
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDragListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En plus de fournir des fonctionnalités d'une zone de liste windows, la classe d' `CDragListBox` autorise l'utilisateur à des éléments de zone de liste de déplacement, tels que les noms du fichier, dans la zone de liste.  
  
## Syntaxe  
  
```  
class CDragListBox : public CListBox  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDragListBox::CDragListBox](../Topic/CDragListBox::CDragListBox.md)|Construit un objet `CDragListBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDragListBox::BeginDrag](../Topic/CDragListBox::BeginDrag.md)|Appelé par l'infrastructure lorsqu'une opération de glissement démarre.|  
|[CDragListBox::CancelDrag](../Topic/CDragListBox::CancelDrag.md)|Appelé par l'infrastructure lorsqu'une opération de glissement a été annulée.|  
|[CDragListBox::Dragging](../Topic/CDragListBox::Dragging.md)|Appelé par l'infrastructure pendant une opération glisser.|  
|[CDragListBox::DrawInsert](../Topic/CDragListBox::DrawInsert.md)|Dessine le guide d'insertion de la zone de liste de glisser\-déplacer.|  
|[CDragListBox::Dropped](../Topic/CDragListBox::Dropped.md)|Appelé par l'infrastructure après l'élément a été supprimé.|  
|[CDragListBox::ItemFromPt](../Topic/CDragListBox::ItemFromPt.md)|Retourne les détails de l'élément déplacé.|  
  
## Notes  
 Les zones de liste avec cette fonctionnalité permet aux utilisateurs de trier les éléments dans une liste dans qui est ce que façon leur est très utile.  Par défaut, la zone de liste seront quant à l'élément vers le nouvel emplacement dans la liste.  Toutefois, les objets d' `CDragListBox` peuvent être personnalisés aux éléments de copie au lieu de les déplacer.  
  
 Le contrôle zone de liste déroulante associé à la classe d' `CDragListBox` ne doit pas avoir **LBS\_SORT** ou le style de **LBS\_MULTIPLESELECT** .  Pour une description des styles de la zone de liste, consultez [styles de la zone de liste](../../mfc/reference/list-box-styles.md).  
  
 Pour utiliser une zone de liste de glisser\-déplacer dans une boîte de dialogue existante de votre application, ajoutez un contrôle de zone de liste à votre modèle de boîte de dialogue à l'aide de l'éditeur de boîtes de dialogue puis assignez une variable membre \(catégorie `Control` et de type de variable `CDragListBox`\) correspondant au type de contrôle zone de liste déroulante dans votre modèle de boîte de dialogue.  
  
 Pour plus d'informations sur les contrôles d'assignation aux variables membres, consultez [Raccourcissez pour définir des variables membres pour les contrôles de boîte de dialogue](../../mfc/defining-member-variables-for-dialog-controls.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple TSTCON](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)
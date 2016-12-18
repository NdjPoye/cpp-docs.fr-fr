---
title: "CImageList Class | Microsoft Docs"
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
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList class"
  - "image lists [C++], CImageList class"
  - "Windows common controls [C++], CImageList"
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
caps.latest.revision: 19
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImageList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle commun de liste d'images windows.  
  
## Syntaxe  
  
```  
class CImageList : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CImageList::CImageList](../Topic/CImageList::CImageList.md)|Construit un objet `CImageList`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CImageList::Add](../Topic/CImageList::Add.md)|Ajoute une image ou des images à une liste d'images.|  
|[CImageList::Attach](../Topic/CImageList::Attach.md)|Joint une liste d'images à un objet d' `CImageList` .|  
|[CImageList::BeginDrag](../Topic/CImageList::BeginDrag.md)|Commence faisant glisser une image.|  
|[CImageList::Copy](../Topic/CImageList::Copy.md)|Copie une image dans un objet d' `CImageList` .|  
|[CImageList::Create](../Topic/CImageList::Create.md)|Initialise une liste d'images et la attaché à un objet d' `CImageList` .|  
|[CImageList::DeleteImageList](../Topic/CImageList::DeleteImageList.md)|Supprime une liste d'images.|  
|[CImageList::DeleteTempMap](../Topic/CImageList::DeleteTempMap.md)|Appelé par le gestionnaire comme les temps d'inactivité de [CWinApp](../../mfc/reference/cwinapp-class.md) pour supprimer tout objet temporaire d' `CImageList` l'a créé par `FromHandle`.|  
|[CImageList::Detach](../Topic/CImageList::Detach.md)|Détache un objet liste d'images d'un objet d' `CImageList` et retourne un handle à une liste d'images.|  
|[CImageList::DragEnter](../Topic/CImageList::DragEnter.md)|Mises à jour de verrous pendant une opération de glissement et affiche l'image faire glisser à une position spécifiée.|  
|[CImageList::DragLeave](../Topic/CImageList::DragLeave.md)|Déverrouille la fenêtre et masque l'image glisser afin que la fenêtre puisse être mise à jour.|  
|[CImageList::DragMove](../Topic/CImageList::DragMove.md)|Déplace l'image qui fait glisser pendant une opération de glisser\-déplacer.|  
|[CImageList::DragShowNolock](../Topic/CImageList::DragShowNolock.md)|Affiche ou masque l'image glisser pendant une opération de glissement, sans verrouiller la fenêtre.|  
|[CImageList::Draw](../Topic/CImageList::Draw.md)|Dessine l'image qui fait glisser pendant une opération de glisser\-déplacer.|  
|[CImageList::DrawEx](../Topic/CImageList::DrawEx.md)|Dessine un élément de liste d'images dans le contexte spécifié de périphérique.  La fonction utilise le style de dessin spécifiée et fusionne l'image avec la couleur spécifiée.|  
|[CImageList::DrawIndirect](../Topic/CImageList::DrawIndirect.md)|Dessine une image d'une liste d'images.|  
|[CImageList::EndDrag](../Topic/CImageList::EndDrag.md)|Termine une opération glisser.|  
|[CImageList::ExtractIcon](../Topic/CImageList::ExtractIcon.md)|Crée une icône sur une image et le masque dans une liste d'images.|  
|[CImageList::FromHandle](../Topic/CImageList::FromHandle.md)|Retourne un pointeur vers un objet d' `CImageList` une fois donné un handle à une liste d'images.  Si un objet d' `CImageList` n'est pas attaché au handle, un objet temporaire d' `CImageList` est créé et joint.|  
|[CImageList::FromHandlePermanent](../Topic/CImageList::FromHandlePermanent.md)|Retourne un pointeur vers un objet d' `CImageList` une fois donné un handle à une liste d'images.  Si un objet d' `CImageList` n'est pas attaché au handle, **NULL** est retourné.|  
|[CImageList::GetBkColor](../Topic/CImageList::GetBkColor.md)|Extrait la couleur d'arrière\-plan pour une liste d'images.|  
|[CImageList::GetDragImage](../Topic/CImageList::GetDragImage.md)|Obtient la liste d'images temporaire qui est utilisée pour faire glisser.|  
|[CImageList::GetImageCount](../Topic/CImageList::GetImageCount.md)|Récupère le nombre d'images dans une liste d'images.|  
|[CImageList::GetImageInfo](../Topic/CImageList::GetImageInfo.md)|Récupère des informations sur une image.|  
|[CImageList::GetSafeHandle](../Topic/CImageList::GetSafeHandle.md)|Récupère **m\_hImageList**.|  
|[CImageList::Read](../Topic/CImageList::Read.md)|Lit une liste d'images d'une archive.|  
|[CImageList::Remove](../Topic/CImageList::Remove.md)|Supprime une image d'une liste d'images.|  
|[CImageList::Replace](../Topic/CImageList::Replace.md)|Remplace une image dans une liste d'images par une nouvelle image.|  
|[CImageList::SetBkColor](../Topic/CImageList::SetBkColor.md)|Définit la couleur d'arrière\-plan pour une liste d'images.|  
|[CImageList::SetDragCursorImage](../Topic/CImageList::SetDragCursorImage.md)|Crée une nouvelle image glisser.|  
|[CImageList::SetImageCount](../Topic/CImageList::SetImageCount.md)|Réinitialise le nombre d'images dans une liste d'images.|  
|[CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md)|Ajoute l'index de base zéro d'une image à la liste d'images à utiliser comme masques de superposition.|  
|[CImageList::Write](../Topic/CImageList::Write.md)|Écrit une liste d'images à une archive.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CImageList::operator HIMAGELIST](../Topic/CImageList::operator%20HIMAGELIST.md)|Retourne `HIMAGELIST` attaché à `CImageList`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CImageList::m\_hImageList](../Topic/CImageList::m_hImageList.md)|Un handle qui contient la liste d'images attachée à cet objet.|  
  
## Notes  
 Une « liste d'images » est une collection d'images de taille même, qui peuvent être mentionnées par son index de base zéro.  Les listes d'images sont utilisées pour gérer efficacement de grands groupes d'icônes ou de bitmap.  Toutes les images dans une liste d'images sont contenues dans une bitmap unique et large dans le format d'écran.  Une liste d'images peut également inclure une bitmap monochrome qui contient les caractères génériques utilisés pour dessiner des images de façon transparente \(style d'icône\).  L'interface de programmation d'applications \(API\) de Microsoft Win32 fournit des fonctions de liste d'images qui vous permettent de dessiner des images, de créer et détruire des listes d'images, d'ajouter et supprimer des images, substituez des images, des images de fusion, et des images glissers.  
  
 Ce contrôle \(et par conséquent la classe d' `CImageList` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95\/98 et Windows NT et versions ultérieures.  
  
 Pour plus d'informations sur l'utilisation `CImageList`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utiliser CImageList](../../mfc/using-cimagelist.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)
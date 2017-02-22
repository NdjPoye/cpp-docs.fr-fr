---
title: "CCheckListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCheckListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckListBox class"
  - "checklist boxes"
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CCheckListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une zone de liste de vérification windows.  
  
## Syntaxe  
  
```  
  
class CCheckListBox : public CListBox  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCheckListBox::CCheckListBox](../Topic/CCheckListBox::CCheckListBox.md)|Construit un objet `CCheckListBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCheckListBox::Create](../Topic/CCheckListBox::Create.md)|Crée la zone de liste de vérification windows et l'attache à l'objet d' `CCheckListBox` .|  
|[CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md)|Appelé par l'infrastructure lorsqu'un aspect visuel d'une zone de liste owner\-draw change.|  
|[CCheckListBox::Enable](../Topic/CCheckListBox::Enable.md)|Active ou désactive un élément de zone de liste de vérification.|  
|[CCheckListBox::GetCheck](../Topic/CCheckListBox::GetCheck.md)|Obtient l'état de la case à cocher d'un élément.|  
|[CCheckListBox::GetCheckStyle](../Topic/CCheckListBox::GetCheckStyle.md)|Obtient le style des cases à cocher du contrôle.|  
|[CCheckListBox::IsEnabled](../Topic/CCheckListBox::IsEnabled.md)|Détermine si un élément est activé.|  
|[CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)|Appelé par l'infrastructure lorsqu'une zone de liste avec un style owner draw est créée.|  
|[CCheckListBox::OnGetCheckPosition](../Topic/CCheckListBox::OnGetCheckPosition.md)|Appelé par l'infrastructure pour obtenir la position de la case à cocher d'un élément.|  
|[CCheckListBox::SetCheck](../Topic/CCheckListBox::SetCheck.md)|Définit l'état de la case à cocher d'un élément.|  
|[CCheckListBox::SetCheckStyle](../Topic/CCheckListBox::SetCheckStyle.md)|Définit le style des cases à cocher du contrôle.|  
  
## Notes  
 Une « zone de liste de vérification » affiche une liste d'éléments, tels que des noms de fichiers.  Chaque élément de la liste a une case à cocher en regard de celle\-ci que l'utilisateur peut contrôler ou la suppression.  
  
 `CCheckListBox` est uniquement pour les contrôles owner\-drawn parce que la liste contient plus que des chaînes de texte.  Dans sa forme la plus simple, une zone de liste de vérification contient des chaînes de texte et cases à cocher, mais vous n'avez pas besoin d'avoir le texte du tout.  Par exemple, vous pouvez avoir une liste de petites bitmap avec une case à cocher en regard de chaque élément.  
  
 Pour créer votre propre zone de liste de vérification, vous devez dériver votre propre classe d' `CCheckListBox`.  Pour dériver votre propre classe, entrez un constructeur pour la classe dérivée, puis appelez **Créer**.  
  
 Si vous souhaitez gérer des messages de notification de fenêtres envoyés par une zone de liste à son parent \(généralement une classe dérivée de [CDialog](../../mfc/reference/cdialog-class.md)\), ajoutez une entrée de la table des messages et une fonction membre gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de la table des messages prend la forme suivante :  
  
 Notification**\(**`id`, `memberFxn`**\)**d'**ON\_**  
  
 où `id` spécifie l'ID de fenêtre enfant de l'émission de contrôle la notification et `memberFxn` est le nom de la fonction membre parente que vous avez écrit pour traiter la notification.  
  
 Le prototype de fonction du parent est la suivante :  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Il existe une seule entrée de la table des messages concernant les contrôles spécifiquement **CCheckListBox** \(mais voir les entrées de la table des messages pour [CListBox](../../mfc/reference/clistbox-class.md)\) :  
  
-   **ON\_CLBN\_CHKCHANGE** l'utilisateur a modifié l'état de la case à cocher d'un élément.  
  
 Si votre zone de liste de vérification est une zone de liste de vérification par défaut \(une liste de chaînes avec les cases à cocher de taille d'une valeur par défaut à gauche de chaque\), vous pouvez utiliser la valeur par défaut [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) pour dessiner la zone de liste de vérification.  Sinon, vous devez substituer la fonction de [CListBox::CompareItem](../Topic/CListBox::CompareItem.md) et [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) et [CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md) s'exécute.  
  
 Vous pouvez créer une zone de liste de vérification d'un modèle de boîte de dialogue ou directement dans votre code.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [MFC exemple TSTCON](../../top/visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)
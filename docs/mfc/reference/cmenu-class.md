---
title: "CMenu Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenu class"
  - "HMENU"
  - "menus, classe de base"
  - "menus, de classes"
  - "menus, créer"
  - "menus, gérer"
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une encapsulation des fenêtres `HMENU`.  
  
## Syntaxe  
  
```  
class CMenu : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenu::CMenu](../Topic/CMenu::CMenu.md)|Construit un objet `CMenu`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)|Ajoute un élément à la fin de le menu.|  
|[CMenu::Attach](../Topic/CMenu::Attach.md)|Joint un handle de menu à un objet d' `CMenu` .|  
|[CMenu::CheckMenuItem](../Topic/CMenu::CheckMenuItem.md)|Définit une coche en regard de ou supprime une coche d'un élément de menu dans le menu contextuel.|  
|[CMenu::CheckMenuRadioItem](../Topic/CMenu::CheckMenuRadioItem.md)|Définit une case d'option en regard de l'élément de menu et supprime la case d'option de tous les autres éléments de menu au groupe.|  
|[CMenu::CreateMenu](../Topic/CMenu::CreateMenu.md)|Crée un menu vide et l'attache à un objet d' `CMenu` .|  
|[CMenu::CreatePopupMenu](../Topic/CMenu::CreatePopupMenu.md)|Crée un menu contextuel vide et l'attache à un objet d' `CMenu` .|  
|[CMenu::DeleteMenu](../Topic/CMenu::DeleteMenu.md)|Supprime un élément spécifié dans le menu.  Si l'élément de menu a un menu contextuel associé, perd le handle au menu contextuel et libère la mémoire utilisée par elle.|  
|[CMenu::DeleteTempMap](../Topic/CMenu::DeleteTempMap.md)|Supprime tous les objets temporaires d' `CMenu` créés par la fonction membre d' `FromHandle` .|  
|[CMenu::DestroyMenu](../Topic/CMenu::DestroyMenu.md)|Perd le menu joint à un objet d' `CMenu` et libère toute mémoire que le menu est occupée.|  
|[CMenu::Detach](../Topic/CMenu::Detach.md)|Détache un handle de menu d'un objet d' `CMenu` et retourne le handle.|  
|[CMenu::DrawItem](../Topic/CMenu::DrawItem.md)|Appelé par l'infrastructure lorsqu'un aspect visuel d'un menu owner\-drawn change.|  
|[CMenu::EnableMenuItem](../Topic/CMenu::EnableMenuItem.md)|Active, les désactive, ou estompe des \(gris\) un élément de menu.|  
|[CMenu::FromHandle](../Topic/CMenu::FromHandle.md)|Retourne un pointeur vers un objet d' `CMenu` donné un handle de menu de windows.|  
|[CMenu::GetDefaultItem](../Topic/CMenu::GetDefaultItem.md)|Détermine l'élément de menu par défaut dans le menu spécifié.|  
|[CMenu::GetMenuContextHelpId](../Topic/CMenu::GetMenuContextHelpId.md)|Extrait l'ID de contexte d'aide associé au menu.|  
|[CMenu::GetMenuInfo](../Topic/CMenu::GetMenuInfo.md)|Récupère des informations sur un menu spécifique.|  
|[CMenu::GetMenuItemCount](../Topic/CMenu::GetMenuItemCount.md)|Détermine le nombre d'éléments dans un menu contextuel ou un menu de niveau supérieur.|  
|[CMenu::GetMenuItemID](../Topic/CMenu::GetMenuItemID.md)|Obtient l'identificateur d'élément de menu pour un élément de menu situé à la position spécifiée.|  
|[CMenu::GetMenuItemInfo](../Topic/CMenu::GetMenuItemInfo.md)|Récupère des informations sur un élément de menu.|  
|[CMenu::GetMenuState](../Topic/CMenu::GetMenuState.md)|Retourne l'état de l'élément de menu spécifié ou le nombre d'éléments dans un menu contextuel.|  
|[CMenu::GetMenuString](../Topic/CMenu::GetMenuString.md)|Récupère l'étiquette de l'élément de menu spécifié.|  
|[CMenu::GetSafeHmenu](../Topic/CMenu::GetSafeHmenu.md)|Retourne `m_hMenu` encapsulé par cet objet d' `CMenu` .|  
|[CMenu::GetSubMenu](../Topic/CMenu::GetSubMenu.md)|Extrait un pointeur vers un menu contextuel.|  
|[CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)|Insère un nouvel élément de menu à la position spécifiée, le déplacement d'autres éléments vers le bas du menu.|  
|[CMenu::InsertMenuItem](../Topic/CMenu::InsertMenuItem.md)|Insère un nouvel élément de menu à la position spécifiée dans un menu.|  
|[CMenu::LoadMenu](../Topic/CMenu::LoadMenu.md)|Charge une ressource menu du fichier exécutable et la attaché à un objet d' `CMenu` .|  
|[CMenu::LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)|Charge un menu d'un modèle de menu en mémoire et l'attache à un objet d' `CMenu` .|  
|[CMenu::MeasureItem](../Topic/CMenu::MeasureItem.md)|Appelé par l'infrastructure pour déterminer les dimensions de menu lorsqu'un menu owner\-drawn est créé.|  
|[CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)|Modifie un élément de menu existant à la position spécifiée.|  
|[CMenu::RemoveMenu](../Topic/CMenu::RemoveMenu.md)|Supprime un élément de menu à un menu contextuel associé du menu spécifié.|  
|[CMenu::SetDefaultItem](../Topic/CMenu::SetDefaultItem.md)|Définit l'élément de menu par défaut du menu spécifié.|  
|[CMenu::SetMenuContextHelpId](../Topic/CMenu::SetMenuContextHelpId.md)|Définit l'ID de contexte d'aide à associer au menu.|  
|[CMenu::SetMenuInfo](../Topic/CMenu::SetMenuInfo.md)|Définit des informations sur un menu spécifique.|  
|[CMenu::SetMenuItemBitmaps](../Topic/CMenu::SetMenuItemBitmaps.md)|Associe les bitmaps spécifiées de la coche à un élément de menu.|  
|[CMenu::SetMenuItemInfo](../Topic/CMenu::SetMenuItemInfo.md)|Modification des informations sur un élément de menu.|  
|[CMenu::TrackPopupMenu](../Topic/CMenu::TrackPopupMenu.md)|Affiche un menu contextuel flottant à l'emplacement spécifié et suivre la sélection des éléments dans le menu contextuel.|  
|[CMenu::TrackPopupMenuEx](../Topic/CMenu::TrackPopupMenuEx.md)|Affiche un menu contextuel flottant à l'emplacement spécifié et suivre la sélection des éléments dans le menu contextuel.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenu::operator HMENU](../Topic/CMenu::operator%20HMENU.md)|Récupère le handle de l'objet de menu.|  
|[CMenu::operator \!\=](../Topic/CMenu::operator%20!=.md)|Détermine si deux objets de menu ne sont pas égales.|  
|[CMenu::operator \=\=](../Topic/CMenu::operator%20==.md)|Détermine si deux objets de menu sont égaux.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMenu::m\_hMenu](../Topic/CMenu::m_hMenu.md)|Spécifie le handle au menu joint à l'objet d' `CMenu` .|  
  
## Notes  
 Il fournit les fonctions membres pour créer, le traçage, mettre à jour, et détruire un menu.  
  
 Créez un objet d' `CMenu` sur le frame de pile en tant que des variables locales, puis fonctions membres d'`CMenu` d'appel pour manipuler le nouveau menu selon les besoins.  Ensuite, appelez [CWnd::SetMenu](../Topic/CWnd::SetMenu.md) pour définir le menu à une fenêtre, suivi immédiatement par un appel à la fonction membre de [détachez](../Topic/CMenu::Detach.md) de l'objet d' `CMenu` .  La fonction membre d' `CWnd::SetMenu` définit le menu de fenêtre vers le nouveau menu, entraîne la fenêtre d'être redessinée pour refléter la modification de menu, et passe également la propriété du menu dans la fenêtre.  L'appel à **Détacher** détache `HMENU` de l'objet d' `CMenu` , de sorte que lorsque la variable locale d' `CMenu` passe hors de portée, le destructeur d'objet d' `CMenu` ne tente pas de détruire un menu qu'il ne possède plus.  Le menu lui\-même est automatiquement détruit lorsque la fenêtre est détruite.  
  
 Vous pouvez utiliser la fonction membre de [LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md) pour créer un menu à partir d'un modèle en mémoire, mais un menu création d'une ressource par un appel à [LoadMenu](../Topic/CMenu::LoadMenu.md) plus facilement est mis à jour, et la ressource menu lui\-même peut être créée et modifiées par l'éditeur de menus.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple CTRLTEST MFC](../../top/visual-cpp-samples.md)   
 [DYNAMENU exemple MFC](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)
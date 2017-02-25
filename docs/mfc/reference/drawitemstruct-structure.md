---
title: "DRAWITEMSTRUCT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DRAWITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DRAWITEMSTRUCT (structure)"
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# DRAWITEMSTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `DRAWITEMSTRUCT` fournit les informations que doit posséder la fenêtre propriétaire pour savoir comment dessiner un contrôle ou un élément de menu de type owner\-drawn.  
  
## Syntaxe  
  
```  
  
typedef struct tagDRAWITEMSTRUCT {  
   UINT   
CtlType  
;  
   UINT   
CtlID  
;  
   UINT   
itemID  
;  
   UINT   
itemAction  
;  
   UINT   
itemState  
;  
   HWND   
hwndItem  
;  
   HDC   
hDC  
;  
   RECT   
rcItem  
;  
   DWORD   
itemData  
;  
} DRAWITEMSTRUCT;  
  
```  
  
#### Paramètres  
 `CtlType`  
 Type du contrôle. Les valeurs pour les types de contrôle sont les suivantes :  
  
-   **ODT\_BUTTON** : bouton de type owner\-drawn.  
  
-   **ODT\_COMBOBOX** : zone de liste modifiable de type owner\-drawn.  
  
-   **ODT\_COMBOBOX** : zone de liste de type owner\-drawn.  
  
-   **ODT\_MENU** : menu de type owner\-drawn.  
  
-   **ODT\_LISTVIEW** : contrôle de d’affichage de liste.  
  
-   **ODT\_STATIC** : contrôle statique de type owner\-drawn.  
  
-   **ODT\_TAB** : contrôle Onglet.  
  
 `CtlID`  
 ID de contrôle pour une zone de liste modifiable, une zone de liste ou un bouton. Ce membre n’est pas utilisé pour un menu.  
  
 `itemID`  
 ID d’élément de menu pour un menu ou index de l’élément d’une zone de liste ou d’une zone de liste modifiable. Pour une zone de liste ou une zone de liste modifiable vide, ce membre est une valeur négative, ce qui permet à l’application de dessiner uniquement le rectangle de focus aux coordonnées spécifiées par le membre **rcItem**, même s’il n’y a aucun élément dans le contrôle. L’utilisateur peut donc voir si la zone de liste ou la zone de liste modifiable a le focus d’entrée. Le paramètre des bits dans le membre **itemAction** détermine si le rectangle doit être dessiné comme si la zone de liste ou la zone de liste modifiable avait le focus d’entrée.  
  
 `itemAction`  
 Définit l’action de dessin nécessaire. Ce sera un ou plusieurs des bits suivants :  
  
-   **ODA\_DRAWENTIRE** : ce bit est défini quand le contrôle doit être dessiné entièrement.  
  
-   **ODA\_FOCUS** : ce bit est défini quand le contrôle obtient ou perd le focus d’entrée. Le membre **itemState** doit être vérifié pour déterminer si le contrôle a le focus.  
  
-   **ODA\_SELECT** : ce bit n’est défini qu’à l’occasion du changement de l’état de sélection. Le membre **itemState** doit être vérifié pour déterminer le nouvel état de sélection.  
  
 *itemState*  
 Spécifie l’état visuel de l’élément à l’issue de l’action de dessin en cours. Autrement dit, si un élément de menu doit être estompé, l’indicateur d’état **ODS\_GRAYED** est défini. Les indicateurs d’état sont les suivants :  
  
-   **ODS\_CHECKED** : ce bit est défini si l’élément de menu doit être vérifié. Ce bit est utilisé uniquement dans un menu.  
  
-   **ODS\_DISABLED** : ce bit est défini si l’élément doit être dessiné comme étant désactivé.  
  
-   **ODS\_FOCUS** : ce bit est défini si l’élément a le focus d’entrée.  
  
-   **ODS\_GRAYED** : ce bit est défini si l’élément doit être estompé. Ce bit est utilisé uniquement dans un menu.  
  
-   **ODS\_SELECTED** : ce bit est défini si l’état de l’élément est sélectionné.  
  
-   **ODS\_COMBOBOXEDIT** : le dessin est tracé dans le champ de sélection \(contrôle d’édition\) d’une zone de liste modifiable de type owner\-drawn.  
  
-   **ODS\_DEFAULT** l’élément est l’élément par défaut.  
  
 `hwndItem`  
 Spécifie le handle de fenêtre du contrôle pour les zones de liste modifiable, les zones de liste et les boutons. Spécifie le handle du menu \(`HMENU`\) qui contient l’élément pour les menus.  
  
 `hDC`  
 Identifie un contexte de périphérique. Le contexte de périphérique doit être utilisé au moment d’effectuer des opérations de dessin sur le contrôle.  
  
 *rcItem*  
 Rectangle dans le contexte de périphérique spécifié par le membre `hDC` qui définit les limites du contrôle à dessiner. Windows détoure automatiquement tout ce que le propriétaire dessine dans le contexte de périphérique pour les zones de liste modifiable, les zones de liste et les boutons, mais il ne détoure pas les éléments de menu. Le propriétaire ne doit pas dessiner les éléments de menu en dehors des limites du rectangle défini par le membre **rcItem**.  
  
 `itemData`  
 Pour une zone de liste modifiable ou une zone de liste, ce membre contient la valeur qui été passée à la zone de liste par l’une des méthodes suivantes :  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CComboBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 Pour un menu, ce membre contient la valeur qui été passée au menu par l’une des méthodes suivantes :  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
## Notes  
 La fenêtre propriétaire du contrôle ou de l’élément de menu de type owner\-drawn reçoit un pointeur vers cette structure en tant que paramètre `lParam` du message `WM_DRAWITEM`.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)
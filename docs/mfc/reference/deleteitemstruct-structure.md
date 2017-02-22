---
title: "DELETEITEMSTRUCT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DELETEITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DELETEITEMSTRUCT (structure)"
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# DELETEITEMSTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `DELETEITEMSTRUCT` décrit un élément dessiné par le propriétaire supprimé de la zone de liste ou de la zone combinée.  
  
## Syntaxe  
  
```  
  
      typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### Paramètres  
 `CtlType`  
 Spécifie **ODT\_LISTBOX** \(une zone de liste dessinée par le propriétaire\) ou **ODT\_COMBOBOX** \(une zone combinée dessinée par le propriétaire\).  
  
 `CtlID`  
 Spécifie l'identificateur de la zone de liste ou de la zone combinée.  
  
 `itemID`  
 Spécifie l'indice de l'élément supprimé dans la zone de liste ou la zone combinée.  
  
 `hwndItem`  
 Identifie le contrôle.  
  
 `itemData`  
 Spécifie des données définies par l'application pour l'élément.  Cette valeur est transmise au contrôle dans le paramètre **lParam** du message qui ajoute l'élément à la zone de liste ou la zone combinée.  
  
## Notes  
 Lorsqu'un élément est supprimé de la zone de liste ou de la zone combinée ou lorsque la zone de liste ou la zone combinée est détruite, Windows envoie le message `WM_DELETEITEM` au propriétaire de chaque élément supprimé.  Le paramètre **lParam** du message contient un pointeur vers la structure.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)
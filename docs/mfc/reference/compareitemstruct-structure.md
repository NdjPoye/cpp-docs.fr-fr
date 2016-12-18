---
title: "COMPAREITEMSTRUCT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMPAREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMPAREITEMSTRUCT (structure)"
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COMPAREITEMSTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `COMPAREITEMSTRUCT` fournit des identificateurs et des données fournies par l'application pour deux éléments dans une zone de liste ou une zone combinée triée et dessinée par le propriétaire.  
  
## Syntaxe  
  
```  
  
      typedef struct tagCOMPAREITEMSTRUCT {  
    UINT   CtlType;  
    UINT   CtlID;  
    HWND   hwndItem;  
    UINT   itemID1;  
    DWORD  itemData1;  
    UINT   itemID2;  
    DWORD  itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### Paramètres  
 `CtlType`  
 **ODT\_LISTBOX** \(qui spécifie une zone de liste \) ou **ODT\_COMBOBOX** \(qui spécifie une zone combinée dessinée par le propriétaire\).  
  
 `CtlID`  
 ID du contrôle de la zone de liste ou la zone combinée.  
  
 `hwndItem`  
 Handle de fenêtre du contrôle.  
  
 *itemID1*  
 Indice du premier élément dans la zone de liste ou la zone combinée qui est comparée.  
  
 *itemData1*  
 Données fournies par l'application pour le premier élément comparé.  Cette valeur a été passée dans l'appel qui a ajouté l'élément dans la zone combinée ou la zone de liste.  
  
 *itemID2*  
 Indice du second élément dans la zone de liste ou la zone combinée à être comparé.  
  
 *itemData2*  
 Données fournies par l'application pour le second élément comparé.  Cette valeur a été passée dans l'appel qui a ajouté l'élément dans la zone combinée ou la zone de liste.  
  
## Notes  
 Lorsqu'une application ajoute un nouvel élément à une zone de liste ou une zone combinée dessinée par le propriétaire créée avec le style **CBS\_SORT** ou **LBS\_SORT**, Windows envoie au propriétaire un message `WM_COMPAREITEM`.  Le paramètre `lParam` du message contient un pointeur long vers une structure `COMPAREITEMSTRUCT`.  A la réception du message, le propriétaire compare les deux éléments et retourne une valeur indiquant quel élément est trié avant l'autre.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)
---
title: DELETEITEMSTRUCT (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DELETEITEMSTRUCT
dev_langs: C++
helpviewer_keywords: DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93be7b23ae713caea5fa64e437fe792c550589f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT, structure
Le `DELETEITEMSTRUCT` structure décrit un owner-drawn zone de liste ou zone de liste déroulante élément supprimé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `CtlType`  
 Spécifie **odt_combobox** (une zone de liste owner-drawn) ou **ODT_COMBOBOX** (une zone de liste déroulante owner-drawn).  
  
 `CtlID`  
 Spécifie l’identificateur de la zone de liste ou zone de liste déroulante.  
  
 `itemID`  
 Spécifie l’index de l’élément dans la zone de liste ou zone de liste déroulante en cours de suppression.  
  
 `hwndItem`  
 Identifie le contrôle.  
  
 `itemData`  
 Spécifie les données définies par l’application pour l’élément. Cette valeur est passée au contrôle dans le **lParam** paramètre du message qui ajoute l’élément à la zone de liste ou zone de liste déroulante.  
  
## <a name="remarks"></a>Notes  
 Lorsqu’un élément est supprimé de la zone de liste ou zone de liste déroulante ou lorsque la zone de liste ou zone de liste déroulante est détruit, Windows envoie le `WM_DELETEITEM` message au propriétaire de chaque élément supprimé. Le **lParam** paramètre du message contient un pointeur vers cette structure.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)



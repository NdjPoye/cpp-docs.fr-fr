---
title: "RGNDATA, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RGNDATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RGNDATA (structure)"
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RGNDATA, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le `RGNDATA` structure contient un en-tête et un tableau de rectangles qui composent une région. Ces rectangles, triées de haut en bas à gauche à droite, ne se chevauchent pas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 
    typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *RDH*  
 Spécifie un [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) structure. (Pour plus d’informations sur cette structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) Les membres de cette structure, spécifient le type de région (qu’il soit rectangulaire ou trapézoïdal), le nombre de rectangles qui constituent la région, la taille de la mémoire tampon qui contient les structures du rectangle, et ainsi de suite.  
  
 `Buffer`  
 Spécifie un tampon de taille arbitraire qui contient la [RECT](../../mfc/reference/rect-structure1.md) structures qui composent la région.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#CreateFromData)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#GetRegionData)


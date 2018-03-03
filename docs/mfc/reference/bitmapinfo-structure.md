---
title: BITMAPINFO (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9d704fec4a6ae0a95bd393b4a7fffa24884711e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO, structure
Le `BITMAPINFO` structure définit les dimensions et les informations de couleur pour une image bitmap indépendante du périphérique de Windows (DIB).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `bmiHeader`  
 Spécifie un [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) structure qui contient des informations sur les dimensions et le format de couleur d’une image bitmap indépendante du périphérique.  
  
 `bmiColors`  
 Spécifie un tableau de [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) ou `DWORD` des types de données qui définissent les couleurs dans l’image bitmap.  
  
## <a name="remarks"></a>Notes  
 Une image bitmap indépendante du périphérique se compose de deux parties distinctes : une `BITMAPINFO` structure qui décrit les dimensions et les couleurs de l’image bitmap et un tableau d’octets qui spécifient les pixels de la bitmap. Les bits du tableau sont regroupées, mais chaque ligne d’analyse doit être complétée par des zéros de fin une `LONG` limite. Si la hauteur est un nombre positive, l’origine de l’image bitmap est l’angle inférieur gauche. Si la hauteur est négative, l’origine sont l’angle supérieur gauche.  
  
 A *bitmap compressé* est un bitmap dans laquelle le tableau d’octets suit immédiatement la `BITMAPINFO` structure. Bitmaps compressés sont référencés par un pointeur unique.  
  
 Pour plus d’informations sur la `BITMAPINFO` de la structure et les valeurs appropriées pour les membres de la `BITMAPINFOHEADER` et `RGBQUAD` structures, consultez les rubriques suivantes dans la documentation du Kit de développement logiciel Windows.  
  
- [BITMAPINFO (structure)](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) structure  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) structure  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)


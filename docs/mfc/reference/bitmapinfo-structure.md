---
title: "BITMAPINFO, structure | Microsoft Docs"
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
  - "BITMAPINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAPINFO (structure)"
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BITMAPINFO, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `BITMAPINFO` définit les dimensions et des informations sur la couleur d'un .dib \(DIB\) Windows.  
  
## Syntaxe  
  
```  
typedef struct tagBITMAPINFO {  
   BITMAPINFOHEADER bmiHeader;  
   RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### Paramètres  
 `bmiHeader`  
 Spécifie une structure [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) qui contient des informations sur les dimensions et de couleur d'un bitmap indépendante du périphérique.  
  
 `bmiColors`  
 Spécifie un tableau de [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) ou de types de données `DWORD` qui définissent les couleurs dans la bitmap.  
  
## Notes  
 Un .dib se compose de deux parties distinctes: une structure de `BITMAPINFO` qui décrit les dimensions et les couleurs de la bitmap, et un tableau d'octets qui spécifient les pixels dans la bitmap.  Les octets dans le tableau sont compressés ensemble, mais chaque ligne scannée doit être entourée de zéros non significatifs pour se terminer sur une limite `LONG`.  Si la hauteur est positive, l'origine de la bitmap est l'angle inférieur gauche.  Si la hauteur est négative, l'origine est l'angle supérieur gauche.  
  
 Une *bitmap compressée* est une bitmap où le tableau d'octets suit immédiatement la structure de `BITMAPINFO`.  Des bitmaps comprimées sont référencées par un pointeur unique.  
  
 Pour plus d'informations sur la structure `BITMAPINFO` et valeurs appropriées pour les membres de structures de `BITMAPINFOHEADER` et `RGBQUAD`, consultez les rubriques suivantes dans la documentation de [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="b5dd2e8c9cedbac12eb858bd01a029a2" class\="tgtSentence"\>BITMAPINFO \(structure\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
-   Structure de [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)  
  
-   Structure de [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)
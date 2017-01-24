---
title: "CBrush Class | Microsoft Docs"
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
  - "CBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pinceaux, CBrush class"
  - "CBrush class"
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBrush Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule un pinceau de définition de données \(GDI\) Graphics Device Interface windows.  
  
## Syntaxe  
  
```  
class CBrush : public CGdiObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBrush::CBrush](../Topic/CBrush::CBrush.md)|Construit un objet `CBrush`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBrush::CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)|Initialise un pinceau avec le style, la couleur, et au modèle spécifié dans une structure de [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) .|  
|[CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)|Initialise un pinceau à un modèle spécifié par un .dib \(DIB\).|  
|[CBrush::CreateHatchBrush](../Topic/CBrush::CreateHatchBrush.md)|Initialise un pinceau avec le modèle et la couleur hachés spécifiés.|  
|[CBrush::CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)|Initialise un pinceau à un modèle spécifié par une bitmap.|  
|[CBrush::CreateSolidBrush](../Topic/CBrush::CreateSolidBrush.md)|Initialise un pinceau avec la couleur unie spécifiée.|  
|[CBrush::CreateSysColorBrush](../Topic/CBrush::CreateSysColorBrush.md)|Crée un pinceau qui est la couleur système par défaut.|  
|[CBrush::FromHandle](../Topic/CBrush::FromHandle.md)|Retourne un pointeur vers un objet d' `CBrush` une fois donné un handle vers un objet d' `HBRUSH` windows.|  
|[CBrush::GetLogBrush](../Topic/CBrush::GetLogBrush.md)|Obtient une structure de [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBrush::operator HBRUSH](../Topic/CBrush::operator%20HBRUSH.md)|Retourne le handle de fenêtre attaché à l'objet d' `CBrush` .|  
  
## Notes  
 Pour utiliser un objet d' `CBrush` , construisez un objet d' `CBrush` et passez \-la à toute fonction membre d' `CDC` qui requiert un pinceau.  
  
 Les pinceaux peuvent être unie, haché, ou modélisée.  
  
 Pour plus d'informations sur `CBrush`, consultez l' [objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [exemple MFC PROPDLG](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CDC, classe](../../mfc/reference/cdc-class.md)
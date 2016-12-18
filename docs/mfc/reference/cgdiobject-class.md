---
title: "CGdiObject Class | Microsoft Docs"
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
  - "CGdiObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pinceaux, base class for"
  - "CGdiObject class"
  - "polices, base class for"
  - "objets GDI, base class for"
  - "palettes, base class for"
  - "stylets, base class for"
  - "régions, base class for"
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGdiObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une classe de base pour différents genres d'objets de définition de données \(GDI\) Graphics Device Interface windows tels que des images, des zones, les pinceaux, des stylets, les palettes de couleurs, des polices.  
  
## Syntaxe  
  
```  
class CGdiObject : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGdiObject::CGdiObject](../Topic/CGdiObject::CGdiObject.md)|Construit un objet `CGdiObject`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGdiObject::Attach](../Topic/CGdiObject::Attach.md)|Joint un objet Windows GDI à un objet d' `CGdiObject` .|  
|[CGdiObject::CreateStockObject](../Topic/CGdiObject::CreateStockObject.md)|Récupère un handle vers une des stylets, les pinceaux, ou des polices d'actions prédéfinie windows.|  
|[CGdiObject::DeleteObject](../Topic/CGdiObject::DeleteObject.md)|Supprime l'objet Windows GDI attaché à l'objet d' `CGdiObject` de la mémoire en libérant toute la mémoire du système associé à l'objet.|  
|[CGdiObject::DeleteTempMap](../Topic/CGdiObject::DeleteTempMap.md)|Supprime tous les objets temporaires d' `CGdiObject` créés par `FromHandle`.|  
|[CGdiObject::Detach](../Topic/CGdiObject::Detach.md)|Détache un objet Windows GDI d'un objet d' `CGdiObject` et retourne un handle vers l'objet Windows GDI.|  
|[CGdiObject::FromHandle](../Topic/CGdiObject::FromHandle.md)|Retourne un pointeur vers un objet d' `CGdiObject` donné un handle vers un objet Windows GDI.|  
|[CGdiObject::GetObject](../Topic/CGdiObject::GetObject.md)|Remplit mémoire tampon de données qui décrivent l'objet Windows GDI attaché à l'objet d' `CGdiObject` .|  
|[CGdiObject::GetObjectType](../Topic/CGdiObject::GetObjectType.md)|Récupère le type de l'objet GDI.|  
|[CGdiObject::GetSafeHandle](../Topic/CGdiObject::GetSafeHandle.md)|Retourne `m_hObject` à moins qu' `this` soit `NULL`, dans ce cas `NULL` est retourné.|  
|[CGdiObject::UnrealizeObject](../Topic/CGdiObject::UnrealizeObject.md)|Réinitialise l'origine d'un pinceau ou réinitialise une palette logique.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGdiObject::operator \!\=](../Topic/CGdiObject::operator%20!=.md)|Détermine si deux objets GDI logiquement ne sont pas égales.|  
|[CGdiObject::operator \=\=](../Topic/CGdiObject::operator%20==.md)|Détermine si deux objets GDI sont logiquement égaux.|  
|[CGdiObject::operator HGDIOBJ](../Topic/CGdiObject::operator%20HGDIOBJ.md)|Récupère `HANDLE` à l'objet Windows GDI attaché.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGdiObject::m\_hObject](../Topic/CGdiObject::m_hObject.md)|`HANDLE` contenant `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, ou `HFONT` associé à cet objet.|  
  
## Notes  
 Vous ne créez jamais directement `CGdiObject` .  Au contraire, vous créez un objet d'une de ses classes dérivées, telles que `CPen` ou `CBrush`.  
  
 Pour plus d'informations sur `CGdiObject`, consultez [Objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)   
 [CFont Class](../../mfc/reference/cfont-class.md)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CPen Class](../../mfc/reference/cpen-class.md)   
 [CRgn, classe](../../mfc/reference/crgn-class.md)
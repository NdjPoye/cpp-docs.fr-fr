---
title: "CFont Class | Microsoft Docs"
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
  - "CFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFont class"
  - "polices, MFC classes"
  - "GDI, font classes"
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFont Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une police de définition de données \(GDI\) Graphics Device Interface windows et fournit les fonctions membres pour manipuler la police.  
  
## Syntaxe  
  
```  
class CFont : public CGdiObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFont::CFont](../Topic/CFont::CFont.md)|Construit un objet `CFont`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFont::CreateFont](../Topic/CFont::CreateFont.md)|Initialise `CFont` avec les fonctionnalités spécifiées.|  
|[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)|Initialise un objet d' `CFont` avec les caractéristiques données dans une structure d' `LOGFONT` .|  
|[CFont::CreatePointFont](../Topic/CFont::CreatePointFont.md)|Initialise `CFont` avec la hauteur spécifiée, mesuré dans les dixièmes d'un point, et la police.|  
|[CFont::CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)|Même qu' `CreateFontIndirect` mais que le corps du caractère est mesuré en les dixièmes d'un point plutôt que des unités logiques.|  
|[CFont::FromHandle](../Topic/CFont::FromHandle.md)|Retourne un pointeur vers un objet d' `CFont` lorsque donné des fenêtres **HFONT**.|  
|[CFont::GetLogFont](../Topic/CFont::GetLogFont.md)|Remplit `LOGFONT` d'informations sur la police logique attachée à l'objet d' `CFont` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFont::operator HFONT](../Topic/CFont::operator%20HFONT.md)|Retourne le handle de police Windows GDI attaché à l'objet d' `CFont` .|  
  
## Notes  
 Pour utiliser un objet d' `CFont` , construire un objet d' `CFont` et joindre une police windows à celui\-ci à [CreateFont](../Topic/CFont::CreateFont.md), [CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md), [CreatePointFont](../Topic/CFont::CreatePointFont.md), ou [CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md), puis utiliser les fonctions membres de l'objet pour manipuler la police.  
  
 Il est souvent plus facile à utiliser les fonctions d' `CreatePointFont` et d' `CreatePointFontIndirect` qu' `CreateFont` ou `CreateFontIndirect` étant donné qu'ils font la conversion pour la hauteur de la police d'une taille aux unités logiques automatiquement.  
  
 Pour plus d'informations sur `CFont`, consultez l' [objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
---
title: "CPen Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "HPEN"
  - "CPen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPen class"
  - "HPEN"
  - "stylets, MFC"
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPen Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule un stylet de définition de données \(GDI\) Graphics Device Interface windows.  
  
## Syntaxe  
  
```  
class CPen : public CGdiObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPen::CPen](../Topic/CPen::CPen.md)|Construit un objet `CPen`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPen::CreatePen](../Topic/CPen::CreatePen.md)|Crée un cosmétique logique ou un stylet géométrique avec le style, la largeur, les attributs spécifiés du pinceau, et l'attache à l'objet d' `CPen` .|  
|[CPen::CreatePenIndirect](../Topic/CPen::CreatePenIndirect.md)|Crée un stylet avec le style, la largeur, et la couleur donnée dans une structure de [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) , et l'attache à l'objet d' `CPen` .|  
|[CPen::FromHandle](../Topic/CPen::FromHandle.md)|Retourne un pointeur vers un objet d' `CPen` lorsque donné des fenêtres `HPEN`.|  
|[CPen::GetExtLogPen](../Topic/CPen::GetExtLogPen.md)|Obtient à [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) la structure sous\-jacente.|  
|[CPen::GetLogPen](../Topic/CPen::GetLogPen.md)|Obtient à [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) la structure sous\-jacente.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPen::operator HPEN](../Topic/CPen::operator%20HPEN.md)|Retourne le handle de fenêtre attaché à l'objet d' `CPen` .|  
  
## Notes  
 Pour plus d'informations sur l'utilisation `CPen`, consultez l' [objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)
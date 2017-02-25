---
title: "CSize Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSize class"
  - "dimensions"
  - "dimensions, MFC"
  - "SIZE"
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CSize Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Semblable à la structure de [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) windows, qui implémente une coordonnée relative ou une position.  
  
## Syntaxe  
  
```  
class CSize : public tagSIZE  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSize::CSize](../Topic/CSize::CSize.md)|Construit un objet `CSize`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSize::operator \-](../Topic/CSize::operator%20-.md)|Soustrait deux dimensions.|  
|[CSize::operator \!\=](../Topic/CSize::operator%20!=.md)|Contrôles pour l'inégalité entre `CSize` et une taille.|  
|[CSize::operator \+](../Topic/CSize::operator%20+.md)|Ajoute deux dimensions.|  
|[CSize::operator \+\=](../Topic/CSize::operator%20+=.md)|Ajoute une taille à `CSize`.|  
|[CSize::operator \-\=](../Topic/CSize::operator%20-=.md)|Soustrait une taille d' `CSize`.|  
|[CSize::operator \=\=](../Topic/CSize::operator%20==.md)|Contrôles d'égalité entre `CSize` et une taille.|  
  
## Notes  
 Cette classe est dérivée de la structure de **TAILLE** .  Cela signifie que vous pouvez passer `CSize` dans un paramètre qui implique **TAILLE** et les données membres de la structure de **TAILLE** sont les données membres accessibles d' `CSize`.  
  
 Les membres de **cx** et de **CY** de **TAILLE** \(et d' `CSize`\) sont publics.  En outre, `CSize` implémente des fonctions membres pour manipuler la structure de **TAILLE** .  
  
> [!NOTE]
>  Pour plus d'informations sur les classes de services partagés \(comme `CSize`\), consultez [classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## Hiérarchie d'héritage  
 `tagSIZE`  
  
 `CSize`  
  
## Configuration requise  
 **Header:** atltypes.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)
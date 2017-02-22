---
title: "Tables de dispatch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros de table de dispatch"
  - "tables de dispatch"
  - "tables de dispatch (macros)"
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Tables de dispatch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE Automation fournit des méthodes pour appeler des méthodes et pour accéder aux propriétés entre les applications.  Le mécanisme fourni par la bibliothèque MFC \(Microsoft Foundation Class\) pour distribuer ces demandes est « la table de dispatch », qui désigne les étiquettes internes et externes des fonctions et des propriétés de l'objet, ainsi que les types de données des propriétés eux\-mêmes et ceux des arguments de fonctions.  
  
### Tables de dispatch  
  
|||  
|-|-|  
|[DECLARE\_DISPATCH\_MAP](../Topic/DECLARE_DISPATCH_MAP.md)|Indique qu'une table de dispatch est utilisée pour exposer les méthodes et les propriétés d'une classe \(doit être utilisé dans la déclaration de classe\).|  
|[BEGIN\_DISPATCH\_MAP](../Topic/BEGIN_DISPATCH_MAP.md)|Démarre la définition d'une table de dispatch.|  
|[END\_DISPATCH\_MAP](../Topic/END_DISPATCH_MAP.md)|Finit la définition d'une table de dispatch.|  
|[DISP\_FUNCTION](../Topic/DISP_FUNCTION.md)|Utilisé dans une table de dispatch pour définir une fonction OLE automation.|  
|[DISP\_PROPERTY](../Topic/DISP_PROPERTY.md)|Définit une propriété OLE automation.|  
|[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md)|Définit une propriété OLE automation et nomme les fonctions Get\(Prendre\) et Set \(Fixer\).|  
|[DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md)|Définit une propriété OLE automation avec une notification.|  
|[DISP\_PROPERTY\_PARAM](../Topic/DISP_PROPERTY_PARAM.md)|Définit une propriété OLE automation qui accepte des paramètres et nomme les fonctions Get et Set.|  
|[DISP\_DEFVALUE](../Topic/DISP_DEFVALUE.md)|Fait d'une propriété existante la valeur par défaut d'un objet.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
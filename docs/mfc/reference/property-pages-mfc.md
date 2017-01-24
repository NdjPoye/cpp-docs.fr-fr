---
title: "Pages de propri&#233;t&#233;s (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions de transfert de données des pages de propriétés dans MFC"
  - "pages de propriétés, fonctions MFC globales"
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pages de propri&#233;t&#233;s (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés affichent les valeurs actuelles des propriétés spécifiques de contrôle OLE dans une interface personnalisable et graphique pour afficher ou modifier en prenant en charge un mécanisme de mappage de données basé sur l'échange de données de boîtes de dialogue \(DDX\).  
  
 Ce mécanisme de mappage de données mappe des contrôles de page de propriétés aux différentes propriétés du contrôle OLE.  La valeur de la propriété de contrôle reflète l'état ou le contenu du contrôle de page de propriétés.  Le mappage entre les contrôles de page de propriétés et les propriétés sont spécifiés par des appels de fonction **DDP\_** de la fonction membre `DoDataExchange` de la page de propriétés.  Voici une liste de fonctions **DDP\_**que les données d'échange lancent en utilisant la page de propriétés de votre contrôle :  
  
### Transfert de données de la page des propriétés  
  
|||  
|-|-|  
|[DDP\_CBIndex](../Topic/DDP_CBIndex.md)|Lie l'index de la chaîne sélectionnée dans une zone de liste déroulante avec une propriété de contrôle.|  
|[DDP\_CBString](../Topic/DDP_CBString.md)|Lie l'index de la chaîne sélectionnée dans la zone de liste déroulante avec une propriété de contrôle.  La chaîne sélectionnée peut démarrer avec les mêmes lettres que la valeur de la propriété mais n'a pas besoin d'une correspondance totale.|  
|[DDP\_CBStringExact](../Topic/DDP_CBStringExact.md)|Lie l'index de la chaîne sélectionnée dans la zone de liste déroulante avec une propriété de contrôle.  La chaîne sélectionnée et la valeur de chaîne de la propriété doivent correspondre exactement.|  
|[DDP\_Check](../Topic/DDP_Check.md)|Lie une case à cocher dans la page propriétés du contrôle avec la propriété d'un contrôle.|  
|[DDP\_LBIndex](../Topic/DDP_LBIndex.md)|Lie l'index de la chaîne sélectionnée dans une zone de liste avec une propriété de contrôle.|  
|[DDP\_LBString](../Topic/DDP_LBString.md)|Lie l'index de la chaîne sélectionnée dans la zone de liste avec une propriété d'un contrôle.  La chaîne sélectionnée peut démarrer avec les mêmes lettres que la valeur de la propriété mais n'a pas besoin d'une correspondance totale.|  
|[DDP\_LBStringExact](../Topic/DDP_LBStringExact.md)|Lie l'index de la chaîne sélectionnée dans la zone de liste avec une propriété d'un contrôle.  La chaîne sélectionnée et la valeur de chaîne de la propriété doivent correspondre exactement.|  
|[DDP\_PostProcessing](../Topic/DDP_PostProcessing.md)|Termine les valeurs de transmission de la propriété du contrôle.|  
|[DDP\_Radio](../Topic/DDP_Radio.md)|Lie un groupe de cases d'option dans la page propriétés du contrôle avec la propriété d'un contrôle.|  
|[DDP\_Text](../Topic/DDP_Text.md)|Lie un contrôle dans la page propriétés du contrôle avec la propriété d'un contrôle.  Cette fonction gère différents types de propriétés, telles que **double**, **short**, `BSTR`, et **long**.|  
  
 Pour plus d'informations sur la fonction et les pages de propriétés `DoDataExchange`, consultez l'article [Contrôles ActiveX : Pages de propriétés](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Voici une liste des macros utilisées pour créer et gérer des pages de propriétés d'un contrôle OLE :  
  
### Pages de propriétés  
  
|||  
|-|-|  
|[BEGIN\_PROPPAGEIDS](../Topic/BEGIN_PROPPAGEIDS.md)|Démarre la liste des ID de page de propriétés.|  
|[END\_PROPPAGEIDS](../Topic/END_PROPPAGEIDS.md)|Termine la liste des ID de page de propriétés.|  
|[PROPPAGEID](../Topic/PROPPAGEID.md)|Déclare une page de propriétés de la classe de contrôle.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
---
title: "CStringData Class | Microsoft Docs"
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
  - "CStringData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringData class"
  - "shared classes, CStringData"
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringData Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente les données d'un objet chaîne.  
  
## Syntaxe  
  
```  
  
struct CStringData  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddRef](../Topic/CStringData::AddRef.md)|Incrémente le décompte de références de l'objet de données de type chaîne.|  
|[data](../Topic/CStringData::data.md)|Récupère les données caractères d'un objet chaîne.|  
|[IsLocked](../Topic/CStringData::IsLocked.md)|Détermine si la mémoire tampon de l'objet String associé est verrouillée.|  
|[IsShared](../Topic/CStringData::IsShared.md)|Détermine si la mémoire tampon de l'objet String associé est actuellement partagée.|  
|[Verrouiller](../Topic/CStringData::Lock.md)|Verrouille la mémoire tampon de l'objet String associé.|  
|[Release](../Topic/CStringData::Release.md)|Libère l'objet chaîne spécifiée.|  
|[Déverrouillez](../Topic/CStringData::Unlock.md)|Déverrouille la mémoire tampon de l'objet String associé.|  
  
### Membres de données  
  
|||  
|-|-|  
|[nAllocLength](../Topic/CStringData::nAllocLength.md)|Longueur des données allouées dans `XCHAR`s \(sans fin null\)|  
|[nDataLength](../Topic/CStringData::nDataLength.md)|Longueur des données actuellement utilisées dans `XCHAR`s \(sans fin null\)|  
|[nRefs](../Topic/CStringData::nRefs.md)|Le décompte de références actuel de l'objet.|  
|[pStringMgr](../Topic/CStringData::pStringMgr.md)|Pointeur vers le gestionnaire de chaînes de cet objet chaîne.|  
  
## Notes  
 Cette classe doit être utilisée par les développeurs implémentant des gestionnaires de chaînes personnalisés.  Pour plus d'informations sur les gestionnaires de chaînes personnalisés, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Cette classe encapsule plusieurs types d'informations et des données associées à un objet chaîne supérieur, tels que des objets de [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), de [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), ou de [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) .  Chaque objet chaîne supérieur contient un pointeur vers l'objet associé à `CStringData` , ce qui permet à plusieurs objets chaîne pour indiquer le même objet de données de type chaîne.  Cette relation est représentée par le décompte de références \(`nRefs`\) de l'objet d' `CStringData` .  
  
> [!NOTE]
>  Dans certains cas, un type chaîne \(tel que **CFixedString**\) ne partagera pas un objet de données de type chaîne avec plusieurs objets String supérieur.  Pour plus d'informations sur cette opération, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Ces données sont composées de :  
  
-   Le gestionnaire de mémoire \(de type [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)\) de la chaîne.  
  
-   La longueur actuelle \([nDataLength](../Topic/CStringData::nDataLength.md)\) de la chaîne.  
  
-   La longueur allouée \([nAllocLength](../Topic/CStringData::nAllocLength.md)\) de la chaîne.  Pour des raisons de performances, cela peut différer de la longueur de chaîne actuelle  
  
-   Le décompte de références actuel \([nRefs](../Topic/CStringData::nRefs.md)\) de l'objet d' `CStringData` .  Cette valeur est utilisée pour déterminer le nombre d'objets chaîne partagent le même objet d' `CStringData` .  
  
-   La mémoire tampon de caractères réel \([données](../Topic/CStringData::data.md)\) de la chaîne.  
  
    > [!NOTE]
    >  La mémoire tampon de caractères réel de l'objet String est alloué par le gestionnaire de chaînes et est ajouté à l'objet d' `CStringData` .  
  
## Configuration requise  
 **Header:** atlsimpstr.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)
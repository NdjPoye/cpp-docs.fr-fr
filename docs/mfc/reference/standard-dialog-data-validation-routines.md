---
title: "Routines de validation des donn&#233;es de bo&#238;te de dialogue standard | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boîte de dialogue standard, routines de validation des données"
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Routines de validation des donn&#233;es de bo&#238;te de dialogue standard
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les routines de validation de données de boîtes de dialogue \(DDV\) standard utilisées pour les contrôles communs de dialogue MFC.  
  
> [!NOTE]
>  Les routines standard d'échange de données de dialogue sont définies dans le fichier d'en\-tête afxdd\_.h.  Toutefois, les applications doivent inclure afxwin.h.  
  
### Fonctions DDV  
  
|||  
|-|-|  
|[DDV\_MaxChars](../Topic/DDV_MaxChars.md)|Vérifie que le nombre de caractères dans une valeur de contrôle donnée ne dépasse pas un nombre donné.|  
|[DDV\_MinMaxByte](../Topic/DDV_MinMaxByte.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **BYTE** donnée.|  
|[DDV\_MinMaxDateTime](../Topic/DDV_MinMaxDateTime.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas plage temporelle donnée.|  
|[DDV\_MinMaxDouble](../Topic/DDV_MinMaxDouble.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **double** donnée.|  
|[DDV\_MinMaxDWord](../Topic/DDV_MinMaxDWord.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **DWORD** donnée.|  
|[DDV\_MinMaxFloat](../Topic/DDV_MinMaxFloat.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **float** donnée.|  
|[DDV\_MinMaxInt](../Topic/DDV_MinMaxInt.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **int** donnée.|  
|[DDV\_MinMaxLong](../Topic/DDV_MinMaxLong.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **log** donnée.|  
|[DDV\_MinMaxLongLong](../Topic/DDV_MinMaxLongLong.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **LONGLONG** donnée.|  
|[DDV\_MinMaxMonth](../Topic/DDV_MinMaxMonth.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse une pas plage temporelle donnée.|  
|[DDV\_MinMaxShort](../Topic/DDV_MinMaxShort.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **short** donnée.|  
|[DDV\_MinMaxSlider](../Topic/DDV_MinMaxSlider.md)|Vérifie qu'une valeur de contrôle slider est dans la plage spécifiée.|  
|[DDV\_MinMaxUInt](../Topic/DDV_MinMaxUInt.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **UINT** donnée.|  
|[DDV\_MinMaxULongLong](../Topic/DDV_MinMaxULongLong.md)|Vérifie qu'une valeur de contrôle donnée ne dépasse pas une plage **ULONGLONG** donnée.|  
  
## Voir aussi  
 [Routines d'échange de données de boîte de dialogue standard](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
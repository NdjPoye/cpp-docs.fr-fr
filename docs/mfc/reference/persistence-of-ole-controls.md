---
title: "Persistance des contr&#244;les OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles OLE, persistance"
  - "persistance, contrôles OLE"
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Persistance des contr&#244;les OLE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une fonction des contrôles OLE est une propriété de persistance \(ou une sérialisation\), qui permet de contrôler OLE pour lire ou écrire des valeurs de propriété vers et à partir d'un fichier ou pour transmettre en continu.  Une application conteneur peut utiliser la sérialisation pour stocker les valeurs des propriétés d'un contrôle même après que l'application est détruit le contrôle.  Les valeurs de propriété du contrôle OLE peuvent être lues du fichier ou du flux de données lorsqu'une nouvelle instance du contrôle est créée ultérieurement.  
  
### Persistance des contrôles OLE  
  
|||  
|-|-|  
|[PX\_Blob](../Topic/PX_Blob.md)|Échange propriété de contrôle qui stocke des données de \(BLOB\) d'objets blob.|  
|[PX\_Bool](../Topic/PX_Bool.md)|Échange une propriété de type **BOOL**.|  
|[PX\_Color](../Topic/PX_Color.md)|Échange une propriété de couleur d'un contrôle.|  
|[PX\_Currency](../Topic/PX_Currency.md)|Échange une propriété de type **CY**.|  
|[PX\_DataPath](../Topic/PX_DataPath.md)|Échange une propriété de type `CDataPathProperty`.|  
|[PX\_Double](../Topic/PX_Double.md)|Échange une propriété de type **double**.|  
|[PX\_Font](../Topic/PX_Font.md)|Échange une propriété de police d'un contrôle.|  
|[PX\_Float](../Topic/PX_Float.md)|Échange une propriété de type **float**.|  
|[PX\_IUnknown](../Topic/PX_IUnknown.md)|Échange une propriété de type indéfini.|  
|[PX\_Long](../Topic/PX_Long.md)|Échange une propriété de type **long**.|  
|[PX\_Picture](../Topic/PX_Picture.md)|Échange une propriété d'image d'un contrôle.|  
|[PX\_Short](../Topic/PX_Short.md)|Échange une propriété de type **short**.|  
|[PX\_ULong](../Topic/PX_ULong.md)|Échange une propriété de type **ULONG**.|  
|[PX\_UShort](../Topic/PX_UShort.md)|Échange une propriété de type **USHORT**.|  
|[PX\_String](../Topic/PX_String.md)|Échange propriété de chaîne de caractères.|  
|[PX\_VBXFontConvert](../Topic/PX_VBXFontConvert.md)|Échange les propriétés des polices d'un contrôle de VBX dans une propriété de la police de contrôle OLE.|  
  
 En outre, la fonction globale `AfxOleTypeMatchGuid` est fournie pour tester une correspondance entre `TYPEDESC` le GUID spécifié.  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
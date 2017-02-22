---
title: "Inscription des contr&#244;les OLE | Microsoft Docs"
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
  - "contrôles OLE, inscrire"
  - "inscrire des contrôles OLE"
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Inscription des contr&#244;les OLE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les contrôles OLE, comme les autres objets OLE serveurs, sont accessibles par d'autres applications OLE\-compatibles.  Cela s'effectue en enregistrant la bibliothèque de types et la classe du contrôle.  
  
 Les fonctions suivantes permettent d'ajouter et de supprimer la classe de contrôle, les pages de propriétés, et la bibliothèque de types de la base de données d'inscription Windows :  
  
### Inscription des contrôles OLE  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](../Topic/AfxOleRegisterControlClass.md)|Ajoute la classe de contrôle sur la base de données d'inscription.|  
|[AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md)|Ajoute une page de propriétés de contrôle de la base de données d'inscription.|  
|[AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md)|Ajoute la bibliothèque de types du contrôle à la base de données d'inscription.|  
|[AfxOleUnregisterClass](../Topic/AfxOleUnregisterClass.md)|Supprime une classe de contrôle ou une classe page de propriétés de la base de données d'inscription.|  
|[AfxOleUnregisterTypeLib](../Topic/AfxOleUnregisterTypeLib.md)|Supprime la bibliothèque de types à partir de la base de données d'inscription.|  
  
 `AfxOleRegisterTypeLib` est généralement appelée dans l'implémentation d'une DLL de contrôle `DllRegisterServer`.  De même, `AfxOleUnregisterTypeLib` est appelé par `DllUnregisterServer`.  `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, et `AfxOleUnregisterClass` sont généralement appelées par la fonction membre `UpdateRegistry` de la fabrique de la classe ou de la page des propriétés d'un contrôle.  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
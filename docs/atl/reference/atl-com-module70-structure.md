---
title: "_ATL_COM_MODULE70 Structure | Microsoft Docs"
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
  - "ATL::_ATL_COM_MODULE70"
  - "ATL._ATL_COM_MODULE70"
  - "_ATL_COM_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_COM_MODULE70 structure"
  - "ATL_COM_MODULE70 structure"
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_COM_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé par le code lié à COM dans ATL.  
  
## Syntaxe  
  
```  
  
      struct _ATL_COM_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInstTypeLib;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;  
   CRITICAL_SECTION m_csObjMap;  
};  
```  
  
## Membres  
 `cbSize`  
 La taille de la structure, utilisée pour le contrôle de version.  
  
 `m_hInstTypeLib`  
 L'instance de handle dans la bibliothèque de types pour ce module.  
  
 **m\_ppAutoObjMapFirst**  
 Adresse de l'élément de tableau qui indique le début des entrées de mappage d'objets pour ce module.  
  
 **m\_ppAutoObjMapLast**  
 Adresse de l'élément de tableau indiquant la fin des entrées de mappage d'objets pour ce module.  
  
 `m_csObjMap`  
 Section critique pour sérialiser l'accès aux entrées de mappage d'objets.  Utilisé en interne par ATL.  
  
## Notes  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md) est défini comme un typedef d' `_ATL_COM_MODULE70`.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)
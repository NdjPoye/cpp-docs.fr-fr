---
title: "HSE_VERSION_INFO, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HSE_VERSION_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HSE_VERSION_INFO (structure)"
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# HSE_VERSION_INFO, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette structure est désignée par le paramètre `pVer` de la méthode `CHttpServer::GetExtensionVersion`.  Elle fournit le numéro de version ISA et une description textuelle ISA.  
  
## Syntaxe  
  
```  
  
      typedef struct _HSE_VERSION_INFO {  
   DWORD dwExtensionVersion;  
   CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### Paramètres  
 *dwExtensionVersion*  
 Numéro de version du ISA.  
  
 *lpszExtensionDesc*  
 Description textuelle de ISA.  L'implémentation par défaut fournit le texte de l'espace réservé ; substituez `CHttpServer::GetExtensionVersion` pour donner votre propre description.  
  
## Configuration requise  
 **En\-tête :** httpext.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
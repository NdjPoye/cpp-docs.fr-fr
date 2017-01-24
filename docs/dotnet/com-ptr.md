---
title: "com::ptr | Microsoft Docs"
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
  - "ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com::ptr"
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# com::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un wrapper d'un objet COM qui peut être utilisé en tant que membre d'une classe CLR.  Le wrapper automatise également la gestion de la durée de vie de l'objet COM, libérant toutes les références détenues sur l'objet lorsque son destructeur est appelé.  Analogue à [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## Syntaxe  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## Notes  
 [com::ptr, classe](../dotnet/com-ptr-class.md) est défini dans \<le msclr\\COM\\fichier de ptr.h\>.  
  
## Voir aussi  
 [Bibliothèque de prise en charge C\+\+](../dotnet/cpp-support-library.md)
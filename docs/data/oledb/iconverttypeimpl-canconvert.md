---
title: "IConvertTypeImpl::CanConvert | Microsoft Docs"
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
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert (méthode)"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConvertTypeImpl::CanConvert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des informations sur la disponibilité des conversions de type dans une commande ou sur un ensemble de lignes.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### Paramètres  
 Consultez le [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Notes  
 Utilise la conversion de données OLE DB dans `MSADC.DLL`.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IConvertTypeImpl, classe](../../data/oledb/iconverttypeimpl-class.md)
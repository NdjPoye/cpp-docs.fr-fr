---
title: "CAtlException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlException"
  - "ATL::CAtlException"
  - "ATL.CAtlException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlException class"
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe définit une exception ATL.  
  
## Syntaxe  
  
```  
  
class CAtlException  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlException::CAtlException](../Topic/CAtlException::CAtlException.md)|Constructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlException::operator HRESULT](../Topic/CAtlException::operator%20HRESULT.md)|Effectue un cast de l'objet en cours à une valeur HRESULT.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlException::m\_hr](../Topic/CAtlException::m_hr.md)|La variable du type HRESULT créée par l'objet et utilisée pour stocker la condition d'erreur.|  
  
## Notes  
 Un objet d' `CAtlException` représente une condition d'exception liée à une opération ATL.  La classe d' `CAtlException` inclut une donnée membre privée qui stocke le code d'état qui indique la raison de l'exception et un opérateur de cast qui vous permet de gérer l'exception comme s'il s'agissait d'un HRESULT.  
  
 En général vous appellerez `AtlThrow` au lieu de créer un objet d' `CAtlException` directement.  
  
## Configuration requise  
 **Header:** atlexcept.h  
  
## Voir aussi  
 [AtlThrow](../Topic/AtlThrow.md)   
 [Class Overview](../../atl/atl-class-overview.md)
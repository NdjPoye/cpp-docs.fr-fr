---
title: "CComVariant Class | Microsoft Docs"
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
  - "ATL.CComVariant"
  - "ATL::CComVariant"
  - "CComVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComVariant class"
  - "VARIANT macro"
  - "VARIANT macro, ATL"
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe encapsule le type d' `VARIANT` , en fournissant un membre indiquant le type de données stocké.  
  
## Syntaxe  
  
```  
  
class CComVariant : public tagVARIANT  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComVariant::CComVariant](../Topic/CComVariant::CComVariant.md)|Constructeur.|  
|[CComVariant::~CComVariant](../Topic/CComVariant::~CComVariant.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComVariant::Attach](../Topic/CComVariant::Attach.md)|Joint **variant** à l'objet d' `CComVariant` .|  
|[CComVariant::ChangeType](../Topic/CComVariant::ChangeType.md)|Convertit l'objet d' `CComVariant` à un nouveau type.|  
|[CComVariant::Clear](../Topic/CComVariant::Clear.md)|Efface l'objet d' `CComVariant` .|  
|[CComVariant::Copy](../Topic/CComVariant::Copy.md)|Copie **variant** à l'objet d' `CComVariant` .|  
|[CComVariant::CopyTo](../Topic/CComVariant::CopyTo.md)|Copie le contenu de l'objet d' `CComVariant` .|  
|[CComVariant::Detach](../Topic/CComVariant::Detach.md)|Détache **variant** sous\-jacent de l'objet d' `CComVariant` .|  
|[CComVariant::GetSize](../Topic/CComVariant::GetSize.md)|Retourne la taille en nombre d'octets du contenu de l'objet d' `CComVariant` .|  
|[CComVariant::ReadFromStream](../Topic/CComVariant::ReadFromStream.md)|Charge **variant** d'un flux.|  
|[CComVariant::SetByRef](../Topic/CComVariant::SetByRef.md)|Initialise l'objet d' `CComVariant` et définit **vt** membre à **VT\_BYREF**.|  
|[CComVariant::WriteToStream](../Topic/CComVariant::WriteToStream.md)|Enregistre **variant** sous\-jacent dans un flux.|  
  
### Opérateurs publics  
  
|||  
|-|-|  
|[CComVariant::operator \<](../Topic/CComVariant::operator%20%3C.md)|Indique si l'objet d' `CComVariant` est inférieure à **variant**spécifié.|  
|[CComVariant::operator \>](../Topic/CComVariant::operator%20%3E.md)|Indique si l'objet d' `CComVariant` est supérieur à **variant**spécifié.|  
|[opérateur \! \=](../Topic/CComVariant::operator%20!=.md)|Indique si l'objet d' `CComVariant` n'est pas **variant**spécifié.|  
|[opérateur \=](../Topic/CComVariant::operator%20=.md)|Assigne une valeur à l'objet d' `CComVariant` .|  
|[\=\= d'opérateur](../Topic/CComVariant::operator%20==.md)|Indique si l'objet d' `CComVariant` égale **variant**spécifié.|  
  
## Notes  
 `CComVariant` encapsule le type d' `VARIANT and VARIANTARG` , qui se compose d'une union et d'un membre indiquant le type de données stockées dans une union.  **variant**s sont généralement utilisés dans l'automation.  
  
 `CComVariant` dérive du type de **variant** ce qui peut être utilisé partout où **variant** peut être utilisé.  Vous pouvez, par exemple, utiliser la macro de **V\_VT** pour récupérer le type d' `CComVariant` ou vous pouvez accéder au membre de **vt** directement comme vous pouvez à **variant**.  
  
## Hiérarchie d'héritage  
 `tagVARIANT`  
  
 `CComVariant`  
  
## Configuration requise  
 **Header:** atlcomcli.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)
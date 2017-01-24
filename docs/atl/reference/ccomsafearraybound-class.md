---
title: "CComSafeArrayBound Class | Microsoft Docs"
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
  - "ATL.CComSafeArrayBound"
  - "ATL::CComSafeArrayBound"
  - "CComSafeArrayBound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArrayBound class"
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSafeArrayBound Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour une structure de [SAFEARRAYBOUND](http://msdn.microsoft.com/fr-fr/303a9bdb-71d6-4f14-8747-84cf84936c6d) .  
  
## Syntaxe  
  
```  
  
class CComSafeArrayBound : public SAFEARRAYBOUND  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CComSafeArrayBound](../Topic/CComSafeArrayBound::CComSafeArrayBound.md)|Constructeur.|  
|[GetCount](../Topic/CComSafeArrayBound::GetCount.md)|Appelez cette méthode pour retourner le nombre d'éléments.|  
|[GetLowerBound](../Topic/CComSafeArrayBound::GetLowerBound.md)|Appelez cette méthode pour retourner la limite inférieure.|  
|[GetUpperBound](../Topic/CComSafeArrayBound::GetUpperBound.md)|Appelez cette méthode pour retourner la limite supérieure.|  
|[SetCount](../Topic/CComSafeArrayBound::SetCount.md)|Appelez cette méthode pour définir le nombre d'éléments.|  
|[SetLowerBound](../Topic/CComSafeArrayBound::SetLowerBound.md)|Appelez cette méthode pour définir la limite inférieure.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/CComSafeArrayBound::operator%20=.md)|Définit `CComSafeArrayBound` à une nouvelle valeur.|  
  
## Notes  
 Cette classe est un wrapper pour la structure de **SAFEARRAYBOUND** utilisée par [CComSafeArray](../../atl/reference/ccomsafearray-class.md).  Elle fournit des méthodes pour l'interrogation et en définissant la limite supérieure et les limites inférieures de dimension unique d' `CComSafeArray` objet et le nombre d'éléments qu'il contient.  Un objet multidimensionnel d' `CComSafeArray` utilise un tableau d'objets d' `CComSafeArrayBound` , un pour chaque dimension.  Par conséquent, lorsque vous utilisez des méthodes telles que [GetCount](../Topic/CComSafeArrayBound::GetCount.md), sachez que cette méthode ne retourne pas total d'éléments dans un tableau multidimensionnel.  
  
 **Header:** atlsafe.h  
  
## Configuration requise  
 **Header:** atlsafe.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)
---
title: "CFileTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileTimeSpan"
  - "ATL.CFileTimeSpan"
  - "ATL::CFileTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTimeSpan class"
  - "shared classes, CFileTimeSpan"
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour gérer des valeurs relatives de date et d'heure associées à un fichier.  
  
## Syntaxe  
  
```  
  
class CFileTimeSpan  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](../Topic/CFileTimeSpan::CFileTimeSpan.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](../Topic/CFileTimeSpan::GetTimeSpan.md)|Appelez cette méthode pour récupérer l'intervalle de l'objet d' `CFileTimeSpan` .|  
|[CFileTimeSpan::SetTimeSpan](../Topic/CFileTimeSpan::SetTimeSpan.md)|Appelez cette méthode pour définir l'intervalle de l'objet d' `CFileTimeSpan` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTimeSpan::operator \-](../Topic/CFileTimeSpan::operator%20-.md)|Exécute la soustraction sur un objet d' `CFileTimeSpan` .|  
|[CFileTimeSpan::operator \!\=](../Topic/CFileTimeSpan::operator%20!=.md)|Compare si deux objets `CFileTimeSpan` sont inégaux.|  
|[CFileTimeSpan::operator \+](../Topic/CFileTimeSpan::operator%20+.md)|Exécute l'ajout d'un objet d' `CFileTimeSpan` .|  
|[CFileTimeSpan::operator \+\=](../Topic/CFileTimeSpan::operator%20+=.md)|Exécute l'ajout d'un objet d' `CFileTimeSpan` et assigne le résultat à l'objet actuel.|  
|[CFileTimeSpan::operator \<](../Topic/CFileTimeSpan::operator%20%3C.md)|Compare deux objets d' `CFileTimeSpan` pour déterminer les moins.|  
|[CFileTimeSpan::operator \<\=](../Topic/CFileTimeSpan::operator%20%3C=.md)|Compare deux objets d' `CFileTimeSpan` pour déterminer l'égalité ou les moins.|  
|[CFileTimeSpan::operator \=](../Topic/CFileTimeSpan::operator%20=.md)|l'opérateur d'assignation.|  
|[CFileTimeSpan::operator \-\=](../Topic/CFileTimeSpan::operator%20-=.md)|Exécute la soustraction sur un objet d' `CFileTimeSpan` et assigne le résultat à l'objet actuel.|  
|[CFileTimeSpan::operator \=\=](../Topic/CFileTimeSpan::operator%20==.md)|Compare si deux objets `CFileTimeSpan` sont égaux.|  
|[CFileTimeSpan::operator \>](../Topic/CFileTimeSpan::operator%20%3E.md)|Compare deux objets d' `CFileTimeSpan` pour déterminer le plus grand.|  
|[CFileTimeSpan::operator \>\=](../Topic/CFileTimeSpan::operator%20%3E=.md)|Compare deux objets d' `CFileTimeSpan` pour déterminer l'égalité ou le plus grand.|  
  
## Notes  
 Cette classe fournit des méthodes pour gérer des périodes de temps connexes souvent produits en effectuant des opérations concernant sujet de lorsqu'un fichier a été créé, du dernier accès ou dernière modification.  Les méthodes de cette classe sont fréquemment utilisées avec des objets de [classe de CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md) .  
  
## Exemple  
 Consultez l'exemple pour [CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md).  
  
## Configuration requise  
 **Header:** atltime.h  
  
## Voir aussi  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime Class](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)
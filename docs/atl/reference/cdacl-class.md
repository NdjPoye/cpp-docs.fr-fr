---
title: "CDacl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDacl"
  - "CDacl"
  - "ATL.CDacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDacl class"
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour une structure de liste DACL nulle \(liste de contrôle d'accès discrétionnaire\).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CDacl : public CAcl  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDacl::CDacl](../Topic/CDacl::CDacl.md)|Constructeur.|  
|[CDacl::~CDacl](../Topic/CDacl::~CDacl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDacl::AddAllowedAce](../Topic/CDacl::AddAllowedAce.md)|Ajoute un CÆ autorisé \(ACE\) à l'objet d' `CDacl` .|  
|[CDacl::AddDeniedAce](../Topic/CDacl::AddDeniedAce.md)|Ajoute un CÆ refusé à l'objet d' `CDacl` .|  
|[CDacl::GetAceCount](../Topic/CDacl::GetAceCount.md)|Retourne le nombre d'ACE \(ACEs\) dans l'objet d' `CDacl` .|  
|[CDacl::RemoveAce](../Topic/CDacl::RemoveAce.md)|Supprime un détail le CÆ \(ACE\) de l'objet d' `CDacl` .|  
|[CDacl::RemoveAllAces](../Topic/CDacl::RemoveAllAces.md)|Supprime tous les ACE contenus dans l'objet d' `CDacl` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDacl::operator \=](../Topic/CDacl::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 Le modèle de sécurité d'un objet peut contenir une liste DACL.  Une liste DACL contient zéro ACE ou plus \(ACEs\) qui identifient les utilisateurs et les groupes qui peuvent accéder à l'objet.  Si une liste DACL vide \(autrement dit, il contient les ACE zéro\), un accès est accordé explicitement, l'accès est refusé implicitement.  Toutefois, si le modèle de sécurité d'un objet n'a pas de liste DACL, l'objet est déprotégé et un accès total.  
  
 Pour récupérer la liste DACL d'un objet, vous devez être le propriétaire de l'objet ou avoir accès à READ\_CONTROL à l'objet.  Pour modifier la liste DACL d'un objet, vous devez avoir accès à WRITE\_DAC à l'objet.  
  
 Utilisez les méthodes de classe fournies pour créer, ajouter, supprimer, et supprimer des ACE de l'objet d' `CDacl` .  Voir aussi [AtlGetDacl](../Topic/AtlGetDacl.md) et l' [AtlSetDacl](../Topic/AtlSetDacl.md).  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CACL](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Sécurité, exemple](../../top/visual-cpp-samples.md)   
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)
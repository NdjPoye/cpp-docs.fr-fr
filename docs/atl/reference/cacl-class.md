---
title: "CAcl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAcl"
  - "ATL::CAcl"
  - "ATLSECURITY/CAcl"
  - "ATL.CAcl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAcl class"
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAcl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour une structure d' `ACL` \(ACL\).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CAcl  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAcl::CAccessMaskArray](../Topic/CAcl::CAccessMaskArray.md)|Un tableau d' `ACCESS_MASK`S.|  
|[CAcl::CAceFlagArray](../Topic/CAcl::CAceFlagArray.md)|Un tableau d' `BYTE`S.|  
|[CAcl::CAceTypeArray](../Topic/CAcl::CAceTypeArray.md)|Un tableau d' `BYTE`S.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAcl::CAcl](../Topic/CAcl::CAcl.md)|Constructeur.|  
|[CAcl::~CAcl](../Topic/CAcl::~CAcl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAcl::GetAceCount](../Topic/CAcl::GetAceCount.md)|Retourne le nombre d'objets de \(ACE\) ACE d'.|  
|[CAcl::GetAclEntries](../Topic/CAcl::GetAclEntries.md)|Récupère les entrées de \(ACL\) ACL de l'objet d' `CAcl` .|  
|[CAcl::GetAclEntry](../Topic/CAcl::GetAclEntry.md)|Récupère toutes les informations sur une entrée dans un objet d' `CAcl` .|  
|[CAcl::GetLength](../Topic/CAcl::GetLength.md)|Retourne la longueur de liste de contrôle d'accès.|  
|[CAcl::GetPACL](../Topic/CAcl::GetPACL.md)|Retourne un PACL \(pointeur vers une liste de contrôle d'accès\).|  
|[CAcl::IsEmpty](../Topic/CAcl::IsEmpty.md)|Teste l'objet d' `CAcl` pour les entrées.|  
|[CAcl::IsNull](../Topic/CAcl::IsNull.md)|Retourne l'état de l'objet d' `CAcl` .|  
|[CAcl::RemoveAce](../Topic/CAcl::RemoveAce.md)|Supprime un détail le CÆ \(ACE\) de l'objet d' `CAcl` .|  
|[CAcl::RemoveAces](../Topic/CAcl::RemoveAces.md)|Supprime tous les ACE \(ACEs\) d' `CAcl` qui s'appliquent à `CSid`donné.|  
|[CAcl::SetEmpty](../Topic/CAcl::SetEmpty.md)|Marque l'objet d' `CAcl` comme vide.|  
|[CAcl::SetNull](../Topic/CAcl::SetNull.md)|Marque l'objet d' `CAcl` comme `NULL`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAcl::operator const ACL \*](../Topic/CAcl::operator%20const%20ACL%20*.md)|Effectue un objet d' `CAcl` à une structure d' `ACL` .|  
|[CAcl::operator \=](../Topic/CAcl::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 La structure d' **ACL** est l'en\-tête d'une liste de contrôle d'accès \(ACL\).  Une liste de contrôle d'accès inclut une liste séquentielle de zéro [ACE](http://msdn.microsoft.com/library/windows/desktop/aa374868) ou plus \(ACEs\).  La personne ACE dans une liste de contrôle d'accès sont comptées de 0 *à n\-1*, où *n* est le nombre d'ACE dans la liste de contrôle d'accès.  En modifiant une liste de contrôle d'accès, une application fait référence à un ACE \(ACE\) dans la liste de contrôle d'accès par son index.  
  
 Il existe deux types de listes de contrôle d'accès :  
  
-   Discrétionnaire  
  
-   Système  
  
 Une liste de contrôle d'accès discrétionnaire est contrôlée par le propriétaire d'un objet ou de toute personne accès accordé de **WRITE\_DAC** à l'objet.  Elle spécifie les utilisateurs particuliers d'accès et des groupes peuvent doivent un objet.  Par exemple, le propriétaire d'un fichier peut utiliser une liste de contrôle d'accès discrétionnaire pour vérifier que les utilisateurs et les groupes peuvent et ne peuvent pas avoir accès au fichier.  
  
 Un objet peut également avoir des informations de sécurité au niveau de le système qui lui sont associées, sous la forme de contrôle d'accès système contrôlé par un administrateur système.  Un système de contrôle d'accès peut permettre à l'administrateur système pour auditer toutes les tentatives d'accès à un objet.  
  
 Pour plus d'informations, consultez la description de [liste de contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374872) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)
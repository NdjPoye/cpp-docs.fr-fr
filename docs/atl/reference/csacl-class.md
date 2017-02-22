---
title: "CSacl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSacl"
  - "ATL::CSacl"
  - "CSacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSacl class"
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour une structure de SACL \(liste de contrôle d'accès système \(\).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CSacl : public CAcl  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSacl::CSacl](../Topic/CSacl::CSacl.md)|Constructeur.|  
|[CSacl::~CSacl](../Topic/CSacl::~CSacl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSacl::AddAuditAce](../Topic/CSacl::AddAuditAce.md)|Ajoute un \(ACE\) ACE d'audit à l'objet d' `CSacl` .|  
|[CSacl::GetAceCount](../Topic/CSacl::GetAceCount.md)|Retourne le nombre d'ACEs \(ACEs\) dans l'objet d' `CSacl` .|  
|[CSacl::RemoveAce](../Topic/CSacl::RemoveAce.md)|Supprime un détail le CÆ \(ACE\) de l'objet de **CSacl** .|  
|[CSacl::RemoveAllAces](../Topic/CSacl::RemoveAllAces.md)|Supprime tous les ACE contenus dans l'objet d' `CSacl` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSacl::operator \=](../Topic/CSacl::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 SACL contient les ACEs \(ACEs\) qui spécifient les types de tentatives d'accès qui génèrent des enregistrements d'audit dans le journal des événements de sécurité d'un contrôleur de domaine.  Notez que SACL génère des entrées de fichier journal uniquement sur le contrôleur de domaine où la tentative d'accès a eu lieu, pas sur chaque contrôleur de domaine qui contient un réplica de l'objet.  
  
 Pour définir ou récupérer SACL dans le modèle de sécurité d'un objet, le privilège de SE\_SECURITY\_NAME doit être activé dans le jeton d'accès du thread demandeur.  Le groupe administrateurs pour accorder le privilège par défaut, il peut être accordé à d'autres utilisateurs ou groupes.  Pour accorder le privilège n'est pas tout ce qui est requis : avant que l'opération définie par le privilège puisse être exécutée, le privilège doit être activé dans le jeton d'accès de sécurité pour prises en compte.  Le modèle permet aux privilèges d'être activé uniquement pour les opérations de système spécifiques, et d'être puis désactivé lorsqu'ils ne sont plus nécessaires.  Voir [AtlGetSacl](../Topic/AtlGetSacl.md) et l' [AtlSetSacl](../Topic/AtlSetSacl.md) pour obtenir des exemples d'activer SE\_SECURITY\_NAME.  
  
 Utilisez les méthodes de classe fournies pour ajouter, supprimer, créer, et supprimer des ACE de l'objet de **SACL** .  Voir aussi [AtlGetSacl](../Topic/AtlGetSacl.md) et l' [AtlSetSacl](../Topic/AtlSetSacl.md).  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hiérarchie d'héritage  
 [CACL](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)
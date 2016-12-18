---
title: "CTokenPrivileges Class | Microsoft Docs"
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
  - "ATL::CTokenPrivileges"
  - "CTokenPrivileges"
  - "ATL.CTokenPrivileges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenPrivileges class"
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenPrivileges Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour la structure de **TOKEN\_PRIVILEGES** .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CTokenPrivileges  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](../Topic/CTokenPrivileges::CTokenPrivileges.md)|Constructeur.|  
|[CTokenPrivileges::~CTokenPrivileges](../Topic/CTokenPrivileges::~CTokenPrivileges.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenPrivileges::Add](../Topic/CTokenPrivileges::Add.md)|Ajoute un ou plusieurs privilèges à l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::Delete](../Topic/CTokenPrivileges::Delete.md)|Supprime un privilège de l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::DeleteAll](../Topic/CTokenPrivileges::DeleteAll.md)|Supprime tous les privilèges de l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetCount](../Topic/CTokenPrivileges::GetCount.md)|Retourne le nombre d'entrées de privilège dans l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetDisplayNames](../Topic/CTokenPrivileges::GetDisplayNames.md)|Récupère les noms complets des droits contenus dans l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetLength](../Topic/CTokenPrivileges::GetLength.md)|Retourne la taille de mémoire tampon en octets requise contenir la structure de **TOKEN\_PRIVILEGES** représentée par l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetLuidsAndAttributes](../Topic/CTokenPrivileges::GetLuidsAndAttributes.md)|Récupère localement les identificateurs uniques \(LUIDs\) et des balises d'attribut de l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetNamesAndAttributes](../Topic/CTokenPrivileges::GetNamesAndAttributes.md)|Récupère les noms de balises et d'attributs de privilège de l'objet d' `CTokenPrivileges` .|  
|[CTokenPrivileges::GetPTOKEN\_PRIVILEGES](../Topic/CTokenPrivileges::GetPTOKEN_PRIVILEGES.md)|Retourne un pointeur vers une structure de **TOKEN\_PRIVILEGES** .|  
|[CTokenPrivileges::LookupPrivilege](../Topic/CTokenPrivileges::LookupPrivilege.md)|Récupère l'attribut associé à un nom de privilèges.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenPrivileges::operator const TOKEN\_PRIVILEGES \*](../Topic/CTokenPrivileges::operator%20const%20TOKEN_PRIVILEGES%20*.md)|Effectue une valeur à un pointeur à la structure de **TOKEN\_PRIVILEGES** .|  
|[CTokenPrivileges::operator \=](../Topic/CTokenPrivileges::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 [jeton d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d'un processus ou un thread et est alloué à chaque utilisateur stocké sur Windows NT ou un système Windows 2000.  
  
 Le jeton d'accès est utilisé pour décrire différents privilèges de sécurité octroyées à chaque utilisateur.  Un privilège consiste en un nombre 64 bits appelé localement un identificateur unique \([LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)\) et une chaîne de modèles.  
  
 La classe d' `CTokenPrivileges` est un wrapper pour la structure de [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) et contient 0 privilèges ou plus.  Les privilèges peuvent être ajoutés, supprimer, ou interrogés à l'aide de les méthodes de classe fournies.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Sécurité, exemple](../../top/visual-cpp-samples.md)   
 [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID\_AND\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)
---
title: "CTokenGroups Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenGroups"
  - "ATL.CTokenGroups"
  - "CTokenGroups"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenGroups class"
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTokenGroups Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour la structure de **TOKEN\_GROUPS** .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CTokenGroups  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenGroups::CTokenGroups](../Topic/CTokenGroups::CTokenGroups.md)|Constructeur.|  
|[CTokenGroups::~CTokenGroups](../Topic/CTokenGroups::~CTokenGroups.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenGroups::Add](../Topic/CTokenGroups::Add.md)|Ajoute `CSid` ou exister la structure de **TOKEN\_GROUPS** à l'objet d' `CTokenGroups` .|  
|[CTokenGroups::Delete](../Topic/CTokenGroups::Delete.md)|Supprime `CSid` et ses attributs associés de l'objet d' `CTokenGroups` .|  
|[CTokenGroups::DeleteAll](../Topic/CTokenGroups::DeleteAll.md)|Supprime tous les objets d' `CSid` et leurs attributs associés de l'objet d' `CTokenGroups` .|  
|[CTokenGroups::GetCount](../Topic/CTokenGroups::GetCount.md)|Retourne le nombre d'objets d' `CSid` et d'attributs associés contenus dans l'objet de **CTokenGroups** .|  
|[CTokenGroups::GetLength](../Topic/CTokenGroups::GetLength.md)|Retourne la taille de l'objet d' `CTokenGroups` .|  
|[CTokenGroups::GetPTOKEN\_GROUPS](../Topic/CTokenGroups::GetPTOKEN_GROUPS.md)|Extrait un pointeur vers la structure de **TOKEN\_GROUPS** .|  
|[CTokenGroups::GetSidsAndAttributes](../Topic/CTokenGroups::GetSidsAndAttributes.md)|Récupère les objets d' `CSid` attributs et l'appartenance à l'objet d' `CTokenGroups` .|  
|[CTokenGroups::LookupSid](../Topic/CTokenGroups::LookupSid.md)|Récupère les attributs associés à un objet d' `CSid` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTokenGroups::operator const TOKEN\_GROUPS \*](../Topic/CTokenGroups::operator%20const%20TOKEN_GROUPS%20*.md)|Effectue un cast de l'objet d' `CTokenGroups` à un pointeur à la structure de **TOKEN\_GROUPS** .|  
|[CTokenGroups::operator \=](../Topic/CTokenGroups::operator%20=.md)|Opérateur d'assignation|  
  
## Notes  
 [jeton d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d'un processus ou un thread et est alloué à chaque utilisateur stocké sur Windows NT ou un système Windows 2000.  
  
 La classe de **CTokenGroups** est un wrapper pour la structure de [TOKEN\_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) , contenant des informations sur les identificateurs de sécurité de groupe \(SIDs\) dans un jeton d'accès.  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Sécurité, exemple](../../top/visual-cpp-samples.md)   
 [CSid Class](../../atl/reference/csid-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)
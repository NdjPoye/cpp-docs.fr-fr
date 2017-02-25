---
title: "CSid Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSid"
  - "ATL::CSid"
  - "ATL.CSid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSid class"
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSid Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour une structure d' `SID` \(identificateur de sécurité\).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CSid  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSid::CSidArray](../Topic/CSid::CSidArray.md)|Tableau d'objets `CSid`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSid::CSid](../Topic/CSid::CSid.md)|Constructeur.|  
|[CSid::~CSid](../Topic/CSid::~CSid.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSid::AccountName](../Topic/CSid::AccountName.md)|Retourne le nom du compte associé à l'objet d' `CSid` .|  
|[CSid::Domain](../Topic/CSid::Domain.md)|Retourne le nom du champ associé à l'objet d' `CSid` .|  
|[CSid::EqualPrefix](../Topic/CSid::EqualPrefix.md)|Teste les préfixes d' `SID` \(identificateur de sécurité\) pour l'égalité.|  
|[CSid::GetLength](../Topic/CSid::GetLength.md)|Retourne la longueur de l'objet d' `CSid` .|  
|[CSid::GetPSID](../Topic/CSid::GetPSID.md)|Retourne un pointeur vers une structure d' `SID` .|  
|[CSid::GetPSID\_IDENTIFIER\_AUTHORITY](../Topic/CSid::GetPSID_IDENTIFIER_AUTHORITY.md)|Retourne un pointeur vers une structure de **SID\_IDENTIFIER\_AUTHORITY** .|  
|[CSid::GetSubAuthority](../Topic/CSid::GetSubAuthority.md)|Retourne un subauthority spécifié dans une structure de **SID** .|  
|[CSid::GetSubAuthorityCount](../Topic/CSid::GetSubAuthorityCount.md)|Retourne le nombre de subauthority.|  
|[CSid::IsValid](../Topic/CSid::IsValid.md)|Teste l'objet d' `CSid` pour la validité.|  
|[CSid::LoadAccount](../Topic/CSid::LoadAccount.md)|Met à jour l'objet d' `CSid` donné le nom du compte et le champ, ou une structure existante d' `SID` .|  
|[CSid::Sid](../Topic/CSid::Sid.md)|Retourne la chaîne d'IDENTIFICATEUR.|  
|[CSid::SidNameUse](../Topic/CSid::SidNameUse.md)|Retourne une description de l'état de l'objet d' `CSid` .|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/CSid::operator%20=.md)|Opérateur d'assignation|  
|[opérateur SID const \*](../Topic/CSid::operator%20const%20SID%20*.md)|Effectue un objet d' `CSid` à un pointeur vers une structure d' `SID` .|  
  
### Opérateurs globaux  
  
|||  
|-|-|  
|[\=\= d'opérateur](../Topic/CSid::operator%20==.md)|Tests deux objets modèle de sécurité d'égalité|  
|[opérateur \! \=](../Topic/CSid::operator%20!=.md)|Tests deux objets modèle de sécurité pour l'inégalité|  
|[opérateur \<](../Topic/CSid::operator%20%3C.md)|Compare la valeur relative de deux objets modèle de sécurité.|  
|[opérateur \>](../Topic/CSid::operator%20%3E.md)|Compare la valeur relative de deux objets modèle de sécurité.|  
|[\<\= d'opérateur](../Topic/CSid::operator%20%3C=.md)|Compare la valeur relative de deux objets modèle de sécurité.|  
|[\>\= d'opérateur](../Topic/CSid::operator%20%3E=.md)|Compare la valeur relative de deux objets modèle de sécurité.|  
  
## Notes  
 La structure d' `SID` est une structure de longueur variable utilisée pour identifier des utilisateurs ou des groupes.  
  
 Les applications ne doivent pas modifier la structure d' `SID` directement, mais utilisent plutôt les méthodes fournies dans cette classe wrapper.  Voir aussi [AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md), [AtlSetGroupSid](../Topic/AtlSetGroupSid.md), [AtlGetGroupSid](../Topic/AtlGetGroupSid.md), et l' [AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md).  
  
 Pour une introduction au modèle de contrôle d'accès dans windows, consultez [contrôle d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Configuration requise  
 **Header:** atlsecurity.h  
  
## Voir aussi  
 [Sécurité, exemple](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [Operators Alphabetical Reference](../../atl/reference/atl-operators.md)
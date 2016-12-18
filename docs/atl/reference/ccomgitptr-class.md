---
title: "CComGITPtr Class | Microsoft Docs"
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
  - "ATL::CComGITPtr<T>"
  - "CComGITPtr"
  - "ATL.CComGITPtr"
  - "ATL.CComGITPtr<T>"
  - "ATL::CComGITPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComGITPtr class"
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComGITPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour traiter les pointeurs d'interface et le tableau global interface \(GIT\).  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
>  
class CComGITPtr  
```  
  
#### Paramètres  
 `T`  
 Le type du pointeur d'interface à stocker dans la table GIT.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComGITPtr::CComGITPtr](../Topic/CComGITPtr::CComGITPtr.md)|Constructeur.|  
|[CComGITPtr::~CComGITPtr](../Topic/CComGITPtr::~CComGITPtr.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComGITPtr::Attach](../Topic/CComGITPtr::Attach.md)|Appelez cette méthode pour enregistrer le pointeur d'interface dans le tableau global interface \(GIT\).|  
|[CComGITPtr::CopyTo](../Topic/CComGITPtr::CopyTo.md)|Appelez cette méthode pour copier l'interface du tableau global interface \(GIT\) au pointeur passé.|  
|[CComGITPtr::Detach](../Topic/CComGITPtr::Detach.md)|Appelez cette méthode pour dissocier l'interface de l'objet d' `CComGITPtr` .|  
|[CComGITPtr::GetCookie](../Topic/CComGITPtr::GetCookie.md)|Appelez cette méthode pour retourner le cookie de l'objet d' `CComGITPtr` .|  
|[CComGITPtr::Revoke](../Topic/CComGITPtr::Revoke.md)|Appelez cette méthode pour supprimer l'interface du tableau global interface \(GIT\).|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComGITPtr::operator DWORD](../Topic/CComGITPtr::operator%20DWORD.md)|Retourne le cookie de l'objet d' `CComGITPtr` .|  
|[CComGITPtr::operator \=](../Topic/CComGITPtr::operator%20=.md)|Opérateur d'assignation|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComGITPtr::m\_dwCookie](../Topic/CComGITPtr::m_dwCookie.md)|Cookie.|  
  
## Notes  
 Les objets qui regroupent le marshaleur libre de threads et la nécessité d'utiliser des pointeurs d'interface obtenus à partir de autres objets doivent prendre des mesures supplémentaires pour garantir que les interfaces sont correctement marshalées.  Cela implique généralement stocker des pointeurs d'interface dans la table GIT et obtenir le pointeur de la table GIT chaque fois qu'il est utilisé.  La classe `CComGITPtr` est fournie pour vous aider à des pointeurs d'interface d'utilisation stockés dans la table GIT.  
  
> [!NOTE]
>  La fonctionnalité générale de la table d'interface est uniquement disponible sur Windows 95 avec la version 1,1 de DCOM et versions ultérieures, Windows 98, Windows NT 4,0 avec Service Pack 3 et versions ultérieures, et Windows 2000.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Marshaleur libre de threads](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Accessing Interfaces Across Apartments](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Class Overview](../../atl/atl-class-overview.md)
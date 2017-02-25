---
title: "CSocketAddr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketAddr"
  - "ATL.CSocketAddr"
  - "ATL::CSocketAddr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocketAddr class"
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSocketAddr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour convertir des noms d'hôte à des adresses de l'hôte, à l'IPv4 de prise en charge et aux formats d'IPV6.  
  
## Syntaxe  
  
```  
  
class CSocketAddr  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocketAddr::CSocketAddr](../Topic/CSocketAddr::CSocketAddr.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocketAddr::FindAddr](../Topic/CSocketAddr::FindAddr.md)|Appelez cette méthode pour convertir le nom d'hôte fourni à l'adresse de l'hôte.|  
|[CSocketAddr::FindINET4Addr](../Topic/CSocketAddr::FindINET4Addr.md)|Appelez cette méthode pour convertir le nom d'hôte IPv4 à l'adresse de l'hôte.|  
|[CSocketAddr::FindINET6Addr](../Topic/CSocketAddr::FindINET6Addr.md)|Appelez cette méthode pour convertir le nom d'hôte de IPv6 à l'adresse de l'hôte.|  
|[CSocketAddr::GetAddrInfo](../Topic/CSocketAddr::GetAddrInfo.md)|Appelez cette méthode pour retourner un pointeur à un élément spécifique dans la liste d' **addrinfo** .|  
|[CSocketAddr::GetAddrInfoList](../Topic/CSocketAddr::GetAddrInfoList.md)|Appelez cette méthode pour retourner un pointeur à la liste d' **addrinfo** .|  
  
## Notes  
 Cette classe fournit une version IP approche agnostique pour examiner les adresses réseau à utiliser avec les wrappers de fonctions API et de socket de Winsocks aux bibliothèques.  
  
 Les membres de cette classe utilisés à des adresses réseau de recherche utilisent la fonction [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)API Win32.  
  
 Cette classe prend en charge les deux adresses réseau d'IPv4 andIPv6.  
  
## Configuration requise  
 **Header:** atlsocket.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)
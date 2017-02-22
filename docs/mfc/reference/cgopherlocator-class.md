---
title: "CGopherLocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherLocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherLocator class"
  - "gopher locator"
  - "Internet, gopher searches"
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CGopherLocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient un Gopher « localisateur » d'un serveur Gopher, détermine le type de localisation, et rend le localisateur disponible à [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres ont été déconseillées car elles ne fonctionnent pas à la plateforme Windows XP, mais ils continueront à travailler sur les plateformes antérieures.  
  
## Syntaxe  
  
```  
class CGopherLocator : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherLocator::CGopherLocator](../Topic/CGopherLocator::CGopherLocator.md)|Construit un objet `CGopherLocator`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherLocator::GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md)|Analyse un localisateur de Gopher et détermine ses attributs.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherLocator::operator LPCTSTR](../Topic/CGopherLocator::operator%20LPCTSTR.md)|Accède directement à des caractères stockés dans un objet d' `CGopherLocator` comme une chaîne de style c.|  
  
## Notes  
 Une application doit obtenir le localisateur d'un serveur Gopher avant de pouvoir récupérer des informations sur ce serveur.  Une fois qu'elle a le localisateur, elle doit traiter le localisateur comme jeton opaque.  
  
 Chaque localisation de Gopher possède les attributs déterminent le type de fichier ou le serveur trouvé.  Consultez [GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md) pour une liste des types de localisateurs de Gopher.  
  
 Une application utilise généralement le localisateur pour les appels à [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md) pour récupérer une information spécifique.  
  
 Pour en savoir plus sur la façon dont `CGopherLocator` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)
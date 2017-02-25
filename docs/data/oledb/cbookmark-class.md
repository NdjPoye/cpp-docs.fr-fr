---
title: "CBookmark, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBookmark"
  - "ATL::CBookmark<nSize>"
  - "CBookmark"
  - "ATL.CBookmark<nSize>"
  - "ATL::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark (classe)"
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CBookmark, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contient une valeur du signet dans sa mémoire tampon.  
  
## Syntaxe  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### Paramètres  
 `nSize`  
 Taille de la mémoire tampon du signet en octets.  Lorsque `nSize` vaut zéro, la mémoire tampon de signet est créée dynamiquement lors de l'exécution.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|Le constructeur|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|Récupère le pointeur vers la mémoire tampon.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Récupère la taille, en octets, de la mémoire tampon.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Définit la valeur du signet.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../../data/oledb/cbookmark-operator-equal.md)|Affecte une classe de `CBookmark` à une autre.|  
  
## Notes  
 **CBookmark\<0\>** est une spécialisation de modèle de `CBookmark`; la mémoire tampon est créée dynamiquement pendant l'exécution.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
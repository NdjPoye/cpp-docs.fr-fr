---
title: "CFixedStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFixedStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class"
  - "shared classes, CFixedStringT"
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CFixedStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet chaîne avec une mémoire tampon de caractères fixe.  
  
## Syntaxe  
  
```  
  
      template< class   
      StringType  
      , int   
      t_nChars  
       >    
class CFixedStringT : private CFixedStringMgr, public StringType  
```  
  
#### Paramètres  
 `StringType`  
 Utilisé comme classe de base pour l'objet String fixe et peut être tout type basé sur d' `CStringT`.  Certains exemples `CString`, `CStringA`, et `CStringW`.  
  
 *t\_nChars*  
 Le nombre de caractères stockés dans la mémoire tampon.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFixedStringT::CFixedStringT](../Topic/CFixedStringT::CFixedStringT.md)|Le constructeur de l'objet String.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFixedStringT::operator \=](../Topic/CFixedStringT::operator%20=.md)|Assigne une valeur à un objet d' `CFixedStringT` .|  
  
## Notes  
 Cette classe est un exemple d'une classe personnalisée de chaînes basées sur `CStringT`.  Bien que assez semblables, les deux classes diffèrent dans l'implémentation.  Les principales différences entre `CFixedStringT` et `CStringT` sont :  
  
-   La mémoire tampon de caractères initial est alloué dans le cadre de l'objet et propose *des t\_nChars*de taille.  Cela permet à l'objet de **CFixedString** pour occuper un segment de mémoire contigu de performance.  Toutefois, si le contenu d'un objet d' `CFixedStringT` augmente au delà *des t\_nChars*, la mémoire tampon est allouée dynamiquement.  
  
-   La mémoire tampon de caractères pour un objet d' `CFixedStringT` est toujours la même longueur \(*t\_nChars*\).  Il n'existe aucune limitation de la taille de mémoire tampon pour les objets d' `CStringT` .  
  
-   Le gestionnaire de mémoire pour `CFixedStringT` est personnalisé tels que partage d'un objet de [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) entre deux objectsis ou plus d' `CFixedStringT` non \- autorisés.  Les objets d'`CStringT` n'ont pas cette limitation.  
  
 Pour plus d'informations sur la personnalisation d' `CFixedStringT` et la gestion de la mémoire pour les objets String afficher en général le [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## Hiérarchie d'héritage  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## Configuration requise  
 **Header:** cstringt.h  
  
## Voir aussi  
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)
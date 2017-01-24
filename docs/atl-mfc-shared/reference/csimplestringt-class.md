---
title: "CSimpleStringT Class | Microsoft Docs"
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
  - "ATL.CSimpleStringT"
  - "ATL::CSimpleStringT"
  - "ATL::CSimpleStringT<BaseType>"
  - "ATL.CSimpleStringT<BaseType>"
  - "CSimpleStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleStringT class"
  - "shared classes, CSimpleStringT"
  - "chaînes (C++), ATL (classe)"
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet d' `CSimpleStringT` .  
  
## Syntaxe  
  
```  
  
      template <typename   
      BaseType  
      >  
class CSimpleStringT  
```  
  
#### Paramètres  
 `BaseType`  
 Le type de caractère de la classe de chaîne.  Il peut s'agir de l'une des valeurs suivantes :  
  
-   `char` \(pour les chaînes de caractères ANSI\).  
  
-   `wchar_t` \(pour les chaînes de caractères Unicode\).  
  
-   **TCHAR** \(pour ANSI et des chaînes de caractères Unicode\).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleStringT::PCXSTR](../Topic/CSimpleStringT::PCXSTR.md)|Un pointeur vers une chaîne constante.|  
|[CSimpleStringT::PXSTR](../Topic/CSimpleStringT::PXSTR.md)|Un pointeur vers une chaîne.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleStringT::CSimpleStringT](../Topic/CSimpleStringT::CSimpleStringT.md)|Construit des objets d' `CSimpleStringT` de plusieurs façons.|  
|[CSimpleStringT::~CSimpleStringT](../Topic/CSimpleStringT::~CSimpleStringT.md)|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleStringT::Append](../Topic/CSimpleStringT::Append.md)|Ajoute un objet d' `CSimpleStringT` à un objet existant d' `CSimpleStringT` .|  
|[CSimpleStringT::AppendChar](../Topic/CSimpleStringT::AppendChar.md)|Ajoute un caractère à un objet existant d' `CSimpleStringT` .|  
|[CSimpleStringT::CopyChars](../Topic/CSimpleStringT::CopyChars.md)|Copie un caractère ou des caractères à une autre chaîne.|  
|[CSimpleStringT::CopyCharsOverlapped](../Topic/CSimpleStringT::CopyCharsOverlapped.md)|Copie un caractère ou des caractères à un autre la chaîne dans laquelle les mémoires tampons se chevauchent.|  
|[CSimpleStringT::Empty](../Topic/CSimpleStringT::Empty.md)|Force une chaîne pour avoir une longueur égale à zéro.|  
|[CSimpleStringT::FreeExtra](../Topic/CSimpleStringT::FreeExtra.md)|Libère toute mémoire supplémentaire précédemment allouée par l'objet chaîne.|  
|[CSimpleStringT::GetAllocLength](../Topic/CSimpleStringT::GetAllocLength.md)|Extrait la longueur allouée d'un objet d' `CSimpleStringT` .|  
|[CSimpleStringT::GetAt](../Topic/CSimpleStringT::GetAt.md)|Retourne le caractère à la position donnée.|  
|[CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md)|Retourne un pointeur vers les caractères dans `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md)|Retourne un pointeur vers les caractères dans `CSimpleStringT`, tronquant à la longueur spécifiée.|  
|[CSimpleStringT::GetLength](../Topic/CSimpleStringT::GetLength.md)|Retourne le nombre de caractères dans un objet d' `CSimpleStringT` .|  
|[CSimpleStringT::GetManager](../Topic/CSimpleStringT::GetManager.md)|Récupère le gestionnaire de mémoire de l'objet d' `CSimpleStringT` .|  
|[CSimpleStringT::GetString](../Topic/CSimpleStringT::GetString.md)|Extrait la chaîne de caractères|  
|[CSimpleStringT::IsEmpty](../Topic/CSimpleStringT::IsEmpty.md)|Teste si un objet d' `CSimpleStringT` ne contient aucun caractère.|  
|[CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md)|Désactive le décompte de références et empêché la chaîne dans la mémoire tampon.|  
|[CSimpleStringT::Preallocate](../Topic/CSimpleStringT::Preallocate.md)|Alloue une quantité de mémoire spécifique pour la mémoire tampon de caractères.|  
|[CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)|Le contrôle de la distribution de la mémoire tampon retourné par `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](../Topic/CSimpleStringT::ReleaseBufferSetLength.md)|Le contrôle de la distribution de la mémoire tampon retourné par `GetBuffer`.|  
|[CSimpleStringT::SetAt](../Topic/CSimpleStringT::SetAt.md)|Définit un caractère à la position donnée.|  
|[CSimpleStringT::SetManager](../Topic/CSimpleStringT::SetManager.md)|Définit le gestionnaire de mémoire d'un objet d' `CSimpleStringT` .|  
|[CSimpleStringT::SetString](../Topic/CSimpleStringT::SetString.md)|Définit la chaîne d'un objet d' `CSimpleStringT` .|  
|[CSimpleStringT::StringLength](../Topic/CSimpleStringT::StringLength.md)|Retourne le nombre de caractères dans la chaîne spécifiée.|  
|[CSimpleStringT::Truncate](../Topic/CSimpleStringT::Truncate.md)|Tronque la chaîne à une longueur spécifiée.|  
|[CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md)|Active le décompte de références et libère la chaîne dans la mémoire tampon.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md)|Accède directement à des caractères stockés dans un objet d' `CSimpleStringT` comme une chaîne de style c.|  
|[CSimpleStringT::operator](../Topic/CSimpleStringT::operator.md)|Retourne le caractère à une position — substitution d'opérateur pour `GetAt`.|  
|[CSimpleStringT::operator \+\=](../Topic/CSimpleStringT::operator%20+=.md)|Concatène une nouvelle chaîne à la fin d'une chaîne existante.|  
|[CSimpleStringT::operator \=](../Topic/CSimpleStringT::operator%20=.md)|Assigne une valeur à un objet d' `CSimpleStringT` .|  
  
## Notes  
 `CSimpleStringT` est la classe de base pour les classes de chaîne prises en charge par Visual C\+\+.  Il fournit la prise en charge minimale de la gestion de la mémoire de l'objet String et la manipulation de base de mémoire tampon.  Pour les objets String plus avancés, consultez [classe de CStringT](../../atl-mfc-shared/reference/cstringt-class.md).  
  
## Configuration requise  
 **Header:** atlsimpstr.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)
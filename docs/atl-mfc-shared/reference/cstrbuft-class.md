---
title: "CStrBufT Class | Microsoft Docs"
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
  - "ATL::CStrBufT<TCharType>"
  - "ATL.CStrBufT"
  - "CStrBufT"
  - "ATL::CStrBufT"
  - "ATL.CStrBufT<TCharType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStrBufT class"
  - "shared classes, CStrBufT"
  - "chaînes (C++), custom memory management"
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStrBufT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit un nettoyage automatique de ressource pour `GetBuffer` et les appels d' `ReleaseBuffer` à `CStringT` objet existant.  
  
## Syntaxe  
  
```  
  
      template<  
   typename TCharType  
>  
class CStrBufT  
```  
  
#### Paramètres  
 *TCharType*  
 Le type de caractère de la classe d' `CStrBufT` .  Il peut s'agir de l'une des valeurs suivantes :  
  
-   `char` \(pour les chaînes de caractères ANSI\)  
  
-   `wchar_t` \(pour les chaînes de caractères Unicode\)  
  
-   **TCHAR** \(pour ANSI et des chaînes de caractères Unicode\)  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`PCXSTR`|Un pointeur vers une chaîne constante.|  
|`PXSTR`|Un pointeur vers une chaîne.|  
|`StringType`|Le type chaîne dont la mémoire tampon doit être manipulée par les spécialisations de ce modèle de classe.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStrBufT::CStrBufT](../Topic/CStrBufT::CStrBufT.md)|Le constructeur pour l'objet de mémoire tampon de chaîne.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStrBufT::SetLength](../Topic/CStrBufT::SetLength.md)|Définit la longueur de la mémoire tampon de caractères de l'objet String associé.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStrBufT::operator PCXSTR](../Topic/CStrBufT::operator%20PCXSTR.md)|Extrait un pointeur de **const** en mémoire tampon de caractères de l'objet String associé.|  
|[CStrBufT::operator PXSTR](../Topic/CStrBufT::operator%20PXSTR.md)|Extrait un pointeur dans la mémoire tampon de caractères de l'objet String associé.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStrBufT::AUTO\_LENGTH](../Topic/CStrBufT::AUTO_LENGTH.md)|Déterminez automatiquement la nouvelle longueur de la chaîne à la version.|  
|[CStrBufT::SET\_LENGTH](../Topic/CStrBufT::SET_LENGTH.md)|Définissez la longueur de l'objet String au moment de GetBuffer|  
  
## Notes  
 Cette classe est utilisée comme classe wrapper pour remplacer les appels à [GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) et [ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md), ou [GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md) et `ReleaseBuffer`.  
  
 Principalement conçu comme classe d'assistance, `CStrBufT` offre un moyen pratique pour un développeur d'utiliser la mémoire tampon de caractères d'un objet chaîne sans vous préoccuper de la façon dont ou de le moment où appeler `ReleaseBuffer`.  C'est possible parce que l'objet de wrapper est hors de portée naturellement dans le cas d'une exception ou d'un multiple quittant les chemins de code ; entraînant son destructeur libérer les ressources de type chaîne.  
  
## Configuration requise  
 **Header:** atlsimpstr.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)
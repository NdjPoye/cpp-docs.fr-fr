---
title: "COleSafeArray Class | Microsoft Docs"
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
  - "COleSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), safe"
  - "COleSafeArray class"
  - "ODBC, safe arrays"
  - "safe arrays"
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleSafeArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe pour l'utilisation des tableaux de type arbitraire et de dimension.  
  
## Syntaxe  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleSafeArray::COleSafeArray](../Topic/COleSafeArray::COleSafeArray.md)|Construit un objet `COleSafeArray`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleSafeArray::AccessData](../Topic/COleSafeArray::AccessData.md)|Extrait un pointeur vers les données de tableau.|  
|[COleSafeArray::AllocData](../Topic/COleSafeArray::AllocData.md)|Alloue de la mémoire pour le tableau.|  
|[COleSafeArray::AllocDescriptor](../Topic/COleSafeArray::AllocDescriptor.md)|Alloue de la mémoire pour le modèle de tableau sécurisé.|  
|[COleSafeArray::Attach](../Topic/COleSafeArray::Attach.md)|Donne le contrôle du tableau existant de **variant** à l'objet d' `COleSafeArray` .|  
|[COleSafeArray::Clear](../Topic/COleSafeArray::Clear.md)|Libère toutes les données dans **variant**sous\-jacent.|  
|[COleSafeArray::Copy](../Topic/COleSafeArray::Copy.md)|Crée une copie d'un tableau existant.|  
|[COleSafeArray::Create](../Topic/COleSafeArray::Create.md)|Crée un tableau sécurisé.|  
|[COleSafeArray::CreateOneDim](../Topic/COleSafeArray::CreateOneDim.md)|Crée un objet unidimensionnel d' `COleSafeArray` .|  
|[COleSafeArray::Destroy](../Topic/COleSafeArray::Destroy.md)|Détruit un tableau existant.|  
|[COleSafeArray::DestroyData](../Topic/COleSafeArray::DestroyData.md)|Perdre des données dans un tableau sécurisé.|  
|[COleSafeArray::DestroyDescriptor](../Topic/COleSafeArray::DestroyDescriptor.md)|Détruit un modèle d'un tableau sécurisé.|  
|[COleSafeArray::Detach](../Topic/COleSafeArray::Detach.md)|Détache le tableau de **variant** de l'objet d' `COleSafeArray` \(afin que les données ne soient pas libérées\).|  
|[COleSafeArray::GetByteArray](../Topic/COleSafeArray::GetByteArray.md)|Copie le contenu du tableau sécurisé dans [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](../Topic/COleSafeArray::GetDim.md)|Retourne le nombre de dimensions du tableau.|  
|[COleSafeArray::GetElement](../Topic/COleSafeArray::GetElement.md)|Extrait un élément unique du tableau sécurisé.|  
|[COleSafeArray::GetElemSize](../Topic/COleSafeArray::GetElemSize.md)|Retourne la taille, en octets, d'un élément dans un tableau sécurisé.|  
|[COleSafeArray::GetLBound](../Topic/COleSafeArray::GetLBound.md)|Retourne la limite inférieure d'une dimension d'un tableau sécurisé.|  
|[COleSafeArray::GetOneDimSize](../Topic/COleSafeArray::GetOneDimSize.md)|Retourne le nombre d'éléments contenus dans l'objet unidimensionnel d' `COleSafeArray` .|  
|[COleSafeArray::GetUBound](../Topic/COleSafeArray::GetUBound.md)|Retourne la limite supérieure pour toute dimension d'un tableau sécurisé.|  
|[COleSafeArray::Lock](../Topic/COleSafeArray::Lock.md)|Incrémente le nombre de verrous d'un tableau et définit un pointeur vers les données de tableau dans le modèle de tableau.|  
|[COleSafeArray::PtrOfIndex](../Topic/COleSafeArray::PtrOfIndex.md)|Retourne un pointeur vers l'élément indexé.|  
|[COleSafeArray::PutElement](../Topic/COleSafeArray::PutElement.md)|Assigne un élément unique dans le tableau.|  
|[COleSafeArray::Redim](../Topic/COleSafeArray::Redim.md)|Modifie le moins significative \(droite\) dépendant d'un tableau sécurisé.|  
|[COleSafeArray::ResizeOneDim](../Topic/COleSafeArray::ResizeOneDim.md)|Modifie le nombre d'éléments dans un objet unidimensionnel d' `COleSafeArray` .|  
|[COleSafeArray::UnaccessData](../Topic/COleSafeArray::UnaccessData.md)|Décrémente le nombre de verrous d'un tableau et invalide le pointeur récupéré par `AccessData`.|  
|[COleSafeArray::Unlock](../Topic/COleSafeArray::Unlock.md)|Décrémente le nombre de verrous d'un tableau elle peut être libérée ou redimensionné.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](../Topic/COleSafeArray::operator%20LPCVARIANT.md)|Accède à la structure sous\-jacente de **variant** de l'objet d' `COleSafeArray` .|  
|[COleSafeArray::operator LPVARIANT](../Topic/COleSafeArray::operator%20LPVARIANT.md)|Accède à la structure sous\-jacente de **variant** de l'objet d' `COleSafeArray` .|  
|[COleSafeArray::operator \=](../Topic/COleSafeArray::operator%20=.md)|Valeurs de copies dans un objet d' `COleSafeArray` \(**SAFEARRAY**, **variant**, `COleVariant`, ou tableau d' `COleSafeArray` \).|  
|[COleSafeArray::operator \=\=](../Topic/COleSafeArray::operator%20==.md)|Compare deux tableaux variantes \(**SAFEARRAY**, **variant**, `COleVariant`, ou tableaux d' `COleSafeArray` \).|  
|[COleSafeArray::operator \<\<](../Topic/COleSafeArray::operator%20%3C%3C.md)|Affiche le contenu d'un objet d' `COleSafeArray` au contexte de dump.|  
  
## Notes  
 `COleSafeArray` dérive de OLE structure de **variant** .  Les fonctions membres OLE **SAFEARRAY** sont disponibles via `COleSafeArray`, ainsi qu'un ensemble de fonctions membres spécialement conçues pour les tableaux unidimensionnels d'octets.  
  
## Hiérarchie d'héritage  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)
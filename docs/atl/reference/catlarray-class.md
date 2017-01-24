---
title: "CAtlArray Class | Microsoft Docs"
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
  - "ATL::CAtlArray"
  - "ATL.CAtlArray"
  - "CAtlArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlArray class"
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un objet table.  
  
## Syntaxe  
  
```  
  
      template<   
   typename E,  
   class ETraits = CElementTraits< E >   
>  
class CAtlArray  
```  
  
#### Paramètres  
 *E*  
 Le type de données à stocker dans le tableau.  
  
 *ETraits*  
 Le code utilisé pour copier ou déplacer des éléments.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Ajouter](../Topic/CAtlArray::Add.md)|Appelez cette méthode pour ajouter un élément à l'objet table.|  
|[Append](../Topic/CAtlArray::Append.md)|Appelez cette méthode pour ajouter du contenu d'un tableau à la fin de les autres.|  
|[AssertValid](../Topic/CAtlArray::AssertValid.md)|Appelez cette méthode pour confirmer que l'objet table est valide.|  
|[CAtlArray](../Topic/CAtlArray::CAtlArray.md)|Constructeur.|  
|[~CAtlArray](../Topic/CAtlArray::~CAtlArray.md)|Le destructeur.|  
|[Copier](../Topic/CAtlArray::Copy.md)|Appelez cette méthode pour copier les éléments d'un tableau vers un autre.|  
|[FreeExtra](../Topic/CAtlArray::FreeExtra.md)|En appelez cette méthode pour supprimer les éléments vides du tableau.|  
|[GetAt](../Topic/CAtlArray::GetAt.md)|Appelez cette méthode pour récupérer un élément unique de l'objet table.|  
|[GetCount](../Topic/CAtlArray::GetCount.md)|Appelez cette méthode pour retourner le nombre d'éléments stockés dans le tableau.|  
|[GetData](../Topic/CAtlArray::GetData.md)|Appelez cette méthode pour retourner un pointeur vers le premier élément du tableau.|  
|[InsertArrayAt](../Topic/CAtlArray::InsertArrayAt.md)|Appelez cette méthode pour insérer un tableau dans une autre.|  
|[InsertAt](../Topic/CAtlArray::InsertAt.md)|Appelez cette méthode pour insérer un nouvel élément \(ou de plusieurs copies d'un élément\) dans l'objet table.|  
|[IsEmpty](../Topic/CAtlArray::IsEmpty.md)|Appelez cette méthode pour vérifier si le tableau est vide.|  
|[RemoveAll](../Topic/CAtlArray::RemoveAll.md)|Appelez cette méthode pour supprimer tous les éléments de l'objet table.|  
|[RemoveAt](../Topic/CAtlArray::RemoveAt.md)|Appelez cette méthode pour supprimer un ou plusieurs éléments du tableau.|  
|[SetAt](../Topic/CAtlArray::SetAt.md)|Appelez cette méthode pour définir la valeur d'un élément dans l'objet table.|  
|[SetAtGrow](../Topic/CAtlArray::SetAtGrow.md)|Appelez cette méthode pour définir la valeur d'un élément dans l'objet table, développant tableau au besoin.|  
|[SetCount](../Topic/CAtlArray::SetCount.md)|Appelez cette méthode pour définir la taille de l'objet table.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur &#91;&#93;](../Topic/CAtlArray::operator.md)|Appelez cet opérateur pour retourner une référence à un élément du tableau.|  
  
### Typedef  
  
|||  
|-|-|  
|[INARGTYPE](../Topic/CAtlArray::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments au tableau.|  
|[OUTARGTYPE](../Topic/CAtlArray::OUTARGTYPE.md)|Le type de données à utiliser pour récupérer des éléments du tableau.|  
  
## Notes  
 **CAtlArray** fournit des méthodes pour créer et gérer un tableau d'éléments d'un type défini par l'utilisateur.  Bien que la présentation des tableaux C standard, l'objet de **CAtlArray** dynamique peut réduire et développer si nécessaire.  L'index du tableau commence toujours à la position 0, et il peut être résolu, ou autorisé à la limite supérieure pour développer lorsque de nouveaux éléments sont ajoutés.  
  
 Pour les tableaux avec un petit nombre d'éléments, la classe [CSimpleArray](../../atl/reference/csimplearray-class.md) ATL peut être utilisée.  
  
 **CAtlArray** est étroitement lié à la classe de **CArray** MFC et exécuté dans un projet MFC, même si sans prise en charge de la sérialisation.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [Exemple MMXSwarm](../../top/visual-cpp-samples.md)   
 [Exemple de DynamicConsumer](../../top/visual-cpp-samples.md)   
 [Exemple UpdatePV](../../top/visual-cpp-samples.md)   
 [Exemple de bannière](../../top/visual-cpp-samples.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
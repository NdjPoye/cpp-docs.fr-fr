---
title: "Creating an Aggregated Object | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], créer"
  - "aggregation [C++], creating aggregated objects"
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating an Aggregated Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le regroupement délègue les appels d' **IUnknown** , en fournissant un pointeur vers **IUnknown** externe de l'objet à l'objet interne.  
  
### Pour créer un objet regroupé en agrégats  
  
1.  Ajoutez un pointeur d' **IUnknown** à votre objet de classe et initialisez\-le à **NULL** dans le constructeur.  
  
2.  Substitution [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md) pour créer l'agrégat.  
  
3.  Utilisez le pointeur d' **IUnknown** , défini dans l'étape 1, comme deuxième paramètre pour les macros de [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md) .  
  
4.  Substitution [FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md) pour libérer le pointeur d' **IUnknown** .  
  
> [!NOTE]
>  Si vous utilisez et release d'une interface de l'objet regroupé en agrégats pendant l' `FinalConstruct`, vous ajoutez la macro de [DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md) à la définition de votre objet de classe.  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)
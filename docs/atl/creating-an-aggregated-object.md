---
title: "Création d’un objet agrégé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b6b66a80c5459157b644ec6b264b707232c83e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-aggregated-object"></a>Création d’un objet
Les délégués d’agrégation **IUnknown** des appels, en fournissant un pointeur vers l’objet externe **IUnknown** à l’objet interne.  
  
### <a name="to-create-an-aggregated-object"></a>Pour créer un objet  
  
1.  Ajouter un **IUnknown** pointeur à votre classe de l’objet et l’initialiser à **NULL** dans le constructeur.  
  
2.  Substituer [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) pour créer l’agrégat.  
  
3.  Utilisez le **IUnknown** pointeur, défini à l’étape 1, comme le second paramètre pour le [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) macros.  
  
4.  Substituer [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) pour libérer le **IUnknown** pointeur.  
  
> [!NOTE]
>  Si vous utilisez et libérer une interface à partir de l’objet agrégée pendant la `FinalConstruct`, vous devez ajouter le [macro DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) (macro) à la définition de votre objet de classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base des objets ATL COM](../atl/fundamentals-of-atl-com-objects.md)


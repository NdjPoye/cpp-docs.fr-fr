---
title: "Understanding Window Traits | Microsoft Docs"
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
  - "window traits"
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Understanding Window Traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes de traits de fenêtre fournissent une méthode simple pour standardiser les styles utilisés pour la création d'un objet window ATL.  Les fonctionnalités de fenêtre sont reçus en tant que paramètres de modèle par [CWindowImpl](../atl/reference/cwindowimpl-class.md) et d'autres classes de fenêtres ATL comme une façon de fournir des styles de fenêtre par défaut au niveau de la classe.  
  
 Si le créateur d'une instance de fenêtre ne fournit pas les styles explicitement dans l'appel à [Create](../Topic/CWindowImpl::Create.md), vous pouvez utiliser une classe Ctraits pour garantir que la fenêtre est toujours créé avec les styles appropriés.  Vous pouvez même que certains styles sont définis pour toutes les instances de cette classe de fenêtre tout en laissant d'autres styles d'être définis pour chaque instance.  
  
## Modèles de traits de fenêtre ATL  
 ATL fournit deux modèles de traits de fenêtre qui permettent aux styles par défaut de positionnement au moment de la compilation à l'aide de leurs paramètres de modèle.  
  
|Classe|Description|  
|------------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|Utilisez ce modèle lorsque vous souhaitez fournir des styles de fenêtre par défaut qui seront utilisés uniquement lorsque aucun autre style n'est spécifiée dans l'appel à **Créer**.  Les styles disponibles au moment de l'exécution sont prioritaires sur les styles définis au moment de la compilation.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Utilisez cette classe lorsque vous souhaitez spécifier des styles qui doivent toujours être définis pour la classe de fenêtre.  Les styles disponibles au moment de l'exécution sont combinés avec les styles définis au moment de la compilation à l'aide de l'opérateur de bits OR.|  
  
 En plus de ces modèles, ATL fournit plusieurs spécialisations intégrées du modèle d' `CWinTraits` pour les combinaisons courantes des styles de fenêtre.  Consultez la documentation de référence de [CWinTraits](../atl/reference/cwintraits-class.md) pour obtenir des informations complètes.  
  
## Traits de fenêtre personnalisés  
 Dans la situation peu probable que la spécialisation d'un des modèles fournis par ATL n'est pas suffisante et vous devez créer votre propre classe Ctraits, vous devez simplement créer une classe qui implémente deux fonctions static : `GetWndStyle` et **GetWndStyleEx**:  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/CPP/understanding-window-traits_1.h)]  
  
 Chacune de ces fonctions est passée une valeur de style au moment de l'exécution qu'il peut utiliser pour produire une nouvelle valeur de style.  Si votre classe de caractères de fenêtre est utilisée comme argument template à une classe de fenêtre ATL, les valeurs de style sont passées à ces fonctions statiques sont celui qui a été passé comme arguments de style à [Create](../Topic/CWindowImpl::Create.md).  
  
## Voir aussi  
 [classes de fenêtre](../atl/atl-window-classes.md)
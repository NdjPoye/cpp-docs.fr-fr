---
title: "Specifying Property Pages | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISpecifyPropertyPages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages method"
  - "pages de propriétés, spécifier"
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Specifying Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez un contrôle ActiveX, vous souhaiterez souvent l'associer à des pages de propriétés qui peuvent être utilisées pour définir les propriétés de votre contrôle.  Les conteneurs de contrôle utilisent l'interface d' **ISpecifyPropertyPages** pour découvrir que des pages de propriétés peuvent être utilisé pour définir les propriétés de votre contrôle.  Vous devrez implémenter cette interface sur votre contrôle.  
  
 Pour implémenter **ISpecifyPropertyPages** à l'aide de ATL, effectuez les étapes suivantes :  
  
1.  Dérivez votre classe d' [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  Ajoutez une entrée pour **ISpecifyPropertyPages** au mappage COM de votre classe.  
  
3.  Ajoutez une entrée de [PROP\_PAGE](../Topic/PROP_PAGE.md) au mappage des propriétés pour chaque page associée à votre contrôle.  
  
> [!NOTE]
>  Lorsque la génération d'un contrôle standard à l'aide de [L'Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md), vous devez uniquement ajouter des entrées d' `PROP_PAGE` au mappage de propriété.  l'assistant génère le code nécessaire pour les autres étapes.  
  
 Les conteneurs polis afficheront les pages de propriétés spécifiées dans le même ordre que les entrées d' `PROP_PAGE` dans le mappage de propriétés.  En général, vous devez mettre les entrées standard de page de propriétés après que les entrées pour vos pages personnalisées dans le mappage de propriété, afin que les utilisateurs voient des pages spécifiques à votre première du contrôle.  
  
## Exemple  
 La classe suivante pour un contrôle calendar utilise l'interface d' **ISpecifyPropertyPages** pour indiquer aux conteneurs que ses propriétés peuvent être définies à une page personnalisée de date et la page de cotations boursières de couleur.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/CPP/specifying-property-pages_1.h)]  
  
## Voir aussi  
 [Pages de propriétés](../atl/atl-com-property-pages.md)   
 [Exemple ATLPages](../top/visual-cpp-samples.md)
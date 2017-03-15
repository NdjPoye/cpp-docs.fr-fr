---
title: "Glisser-d&#233;placer&#160;: personnalisation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "glisser-déplacer, appeler DoDragDrop"
  - "glisser-déplacer, COleDataSource (objet)"
  - "glisser-déplacer, personnaliser le comportement"
  - "glisser-déplacer, implémentation dans des application autres que OLE"
  - "OLE (glisser-déplacer), personnaliser le comportement"
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Glisser-d&#233;placer&#160;: personnalisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'implémentation par défaut de la fonctionnalité glisser\-déplacer est suffisante pour la plupart des applications.  Toutefois, certaines applications peuvent exiger que ce comportement standard soit modifié.  Cet article décrit les étapes nécessaires pour modifier ces valeurs par défaut.  En outre, utilisez cette technique pour générer des applications qui ne prennent pas en charge les documents composés comme sources de suppression.  
  
 Si vous personnalisez le comportement standard de glissement OLE, ou si vous possédez une application non OLE, vous devez créer un objet `COleDataSource` pour contenir les données.  Lorsque l'utilisateur lance une opération de glisser\-déplacer, votre code doit appeler la fonction `DoDragDrop` de cet objet au lieu d'autres classes qui prennent en charge les opérations de glisser\-déplacer.  
  
 Éventuellement, vous pouvez créer un objet `COleDropSource` pour contrôler le déplacement et pour remplacer certaines de ses fonctions selon le type de comportement que vous souhaitez modifier.  Cet objet de source de suppression est ensuite transmis à `COleDataSource::DoDragDrop` pour modifier le comportement par défaut de ces fonctions.  Ces différentes options permettent une grande souplesse dans la façon dont vous prenez en charge les opérations de glisser\-déplacer dans votre application.  Pour plus d'informations sur les sources de données, consultez l'article [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Vous pouvez remplacer les fonctions suivantes pour personnaliser les opérations de glisser\-déplacer :  
  
|Substitution|Pour personnaliser|  
|------------------|------------------------|  
|`OnBeginDrag`|Comment la glisse est initialisée après avoir appelé `DoDragDrop`.|  
|`GiveFeedback`|Commentaires visuel, telles que l'apparence de curseur, pour différents résultats de suppression.|  
|`QueryContinueDrag`|L'arrêt d'une opération de glisser\-déplacer.  Cette fonction vous permet de vérifier des états de clé de modification pendant l'opération de glissement.|  
  
## Voir aussi  
 [Glisser\-déplacer \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource Class](../mfc/reference/coledropsource-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)
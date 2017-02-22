---
title: "Programmes d&#39;assistance pour les classes de collection | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de collection, fonctions d'assistance"
  - "ConstructElements (fonction)"
  - "DestructElements (fonction)"
  - "classe de collection de fonctions d'assistance"
  - "SerializeElements (fonction)"
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Programmes d&#39;assistance pour les classes de collection
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes de collection `CMap`, `CList`, et `CArray` utilisent des fonctions d'assistance globales pour réaliser des choses telles que comparer, copier ou mettre des éléments en série.  Dans le cadre de votre implémentation des classes basée sur `CMap`, `CList`, et `CArray`, vous devez remplacer ces fonctions comme ça se révèle nécessaire avec des versions adaptées au type de données stockées dans votre mappage, liste, ou tableau.  Pour plus d'informations sur le remplacement des fonctions d'assistance tels que `SerializeElements`, consultez l'article [Collections : Comment effectuer une collection en évitant les erreurs de types](../../mfc/how-to-make-a-type-safe-collection.md).  Notez que **ConstructElements** et **DestructElements** sont déconseillés.  
  
 La bibliothèque MFC fournit les fonctions globales suivantes qui permettent de personnaliser vos classes de collection :  
  
### Programmes d'assistance pour les classes de collection  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|Indique si les éléments sont identiques.|  
|[CopyElements](../Topic/CopyElements.md)|Copie les élément d'une table vers une autre.|  
|[DumpElements](../Topic/DumpElements.md)|Fournit en sortie un diagnostique en continu.|  
|[HashKey](../Topic/HashKey.md)|Calcule une clé de hachage.|  
|[SerializeElements](../Topic/SerializeElements.md)|Stocke ou récupère des éléments dans ou à partir d'une archive.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)
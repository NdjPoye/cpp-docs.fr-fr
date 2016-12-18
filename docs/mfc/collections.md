---
title: "Collections | Microsoft Docs"
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
  - "modèles de tableaux"
  - "tableaux (C++), classes"
  - "classes de collection, à propos des classes de collection"
  - "classes de collection, tableaux"
  - "classes de collection, listes"
  - "classes de collection, mappages"
  - "classes de collection, MFC"
  - "classes de collection, formes"
  - "classes de collection, basées sur des modèles"
  - "collections, à propos des collections"
  - "classes de collection MFC"
  - "MFC, collections"
  - "formes"
  - "formes, collection"
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Collections
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC fournit des classes de collection pour gérer des groupes d'objets.  Ces classes sont de deux types :  
  
-   [Classes de collection crées à partir de modèles C\+\+](#_core_the_template.2d.based_collection_classes)  
  
-   [Classes de collection non crées à partir de modèles C\+\+](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  Si votre code utilise déjà les classes de collection basées sur des modèles, vous pouvez continuer à les utiliser.  Si vous spécifiez de nouvelles classes de collection de type sécurisé pour vos propres types de données, nous vous recommandons d'utiliser les plus récentes classes basées sur des modèles.  
  
##  <a name="_core_collection_shapes"></a> Formes de collection  
 Une classe de collection est caractérisée par sa « forme » et par les types de ses éléments.  La forme fait référence à la façon dont les objets sont organisés et stockés par la collection.  MFC fournit trois formes de base de collection : listes, tables, et cartes \(également appelées dictionnaires\).  Choisissez la forme de collection qui est la plus adaptée à votre problème de programmation particulier.  
  
 Chacune des trois formes de collection est décrite brièvement plus loin dans cette rubrique.  Pour comparer les fonctionnalités des formes pour vous aider à déterminer celle qui convient à votre programme, consultez [Recommandations relatives au choix d'une classe de collection](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   Liste  
  
     La classe de pool fournit une liste triée et non indexée d'éléments, implémentée comme des listes doublement chaînées.  Une liste possède une « tête » et une « queue », et ajouter ou supprimer des éléments de la tête ou de la queue, ou insérer ou supprimer des éléments dans le milieu, est très rapide.  
  
-   Tableau  
  
     La classe de tableau fournit un tableau d'objets classés, ordonnés, et indexés par des entiers.  
  
-   Cartes \(également appelées dictionnaire\)  
  
     Une carte est une collection qui associe un objet principal avec un objet de valeur.  
  
##  <a name="_core_the_template.2d.based_collection_classes"></a> Les classes de collections basées sur un modèle  
 La façon la plus simple d'implémenter une collection de type sécurisé qui contient des objets de tout type est d'utiliser l'une des classes MFC basées sur un modèle.  Pour obtenir des exemples de ces classes, consultez l'exemple [RECUEILLEZ](../top/visual-cpp-samples.md)de MFC.  
  
 Le tableau suivant répertorie les classes de collection MFC basées sur des modèles :  
  
### Classes de modèle de collections  
  
|Contenu des collections|Tableaux|Listes|Tables|  
|-----------------------------|--------------|------------|------------|  
|Collections d'objets de n'importe quel type.|`CArray`|`CList`|`CMap`|  
|Collections de pointeurs vers des objets de n'importe quel type|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Les classes de collection non basées sur des modèles  
 Si votre application utilise déjà les classes MFC de collection qui ne se basent pas sur des modèles, vous pouvez continuer à les utiliser.  Toutefois, pour les nouvelles collections, nous vous recommandons d'utiliser les classes basées sur des modèles.  Le tableau suivant répertorie les classes de collection MFC qui ne sont pas basées sur des modèles.  
  
### Classes de collections non basées sur des modèles.  
  
|Tableaux|Listes|Tables|  
|--------------|------------|------------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 Les caractéristiques de la table de classes de collections MFC dans [Recommandations relatives au choix d'une classe de collection](../mfc/recommendations-for-choosing-a-collection-class.md) décrit les classes de collection MFC en termes de fonctionnalités \(autres que la forme\) :  
  
-   Si la classe utilise des modèles C\+\+  
  
-   Si les éléments stockés dans la collection peuvent être sérialisés  
  
-   Si les éléments stockés dans la collection peuvent être mis de côté pour effectuer des diagnostics  
  
-   Si la collection est de type sécurisé  
  
### Que voulez\-vous faire ?  
  
#### Tâches générales de classe de collection  
  
-   [Recommandations relatives au choix d'une classe de collection](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [Comment : définir une collection de type sécurisé](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [Création de collections de piles et de files d'attente](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../Topic/CArray::Add.md)  
  
#### Tâches de classe de collection basées sur un modèle  
  
-   [Classes basées sur un modèle](../mfc/template-based-classes.md)  
  
#### L'accès aux membres d'une collection \(basée sur un modèle ou non\)  
  
-   [Accès à tous les membres d'une collection](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [Suppression de tous les objets d'une collection CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)
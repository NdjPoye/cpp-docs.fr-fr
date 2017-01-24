---
title: "Comment&#160;: d&#233;finir une collection de type s&#233;curis&#233; | Microsoft Docs"
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
  - "classes de collection, dériver à partir de (non basée sur un modèle)"
  - "classes de collection, basées sur des modèles"
  - "classes de collection, sécurité de type"
  - "sérialisation (C++), classes de collection"
  - "SerializeElements (fonction)"
  - "sérialiser des éléments de classe de collection"
  - "collections de type sécurisé"
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;finir une collection de type s&#233;curis&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment effectuer les collections de type sécurisé pour vos propres types de données.  Les rubriques traitées ici sont les suivantes :  
  
-   [Utilisation des classes sur TEMPLATE pour la cohérence des types](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [Implémentation des fonctions d'assistance](#_core_implementing_helper_functions)  
  
-   [Utilisation des classes des collections non typées](#_core_using_nontemplate_collection_classes)  
  
 La bibliothèque MFC fournit les collections de type sécurisé prédéfinies basées sur des modèles C\+\+.  Étant donné qu'ils sont des modèles, l'utilisation de ces classes fournissent la cohérence des types et simplifier l'utilisation sans stéréotype et un autre travail supplémentaire impliquées lors de l'utilisation d'une classe basée sur des modèles à cet effet.  L'exemple [Classe d'événements RECUEILLEZ](../top/visual-cpp-samples.md) de MFC illustre l'utilisation de classes de collection TEMPLATE de dans une application de MFC.  Utilisez en général ces classes lorsque vous entrez un nouveau code de collections.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> Utilisation des classes sur TEMPLATE pour la cohérence des types  
  
#### Pour utiliser les classes sur TEMPLATE  
  
1.  Déclarez une variable du type stocké dans la collection.  Par exemple :  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  Appelez la fonction membre de l'objet de la collection.  Par exemple :  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  Si nécessaire, mettez en œuvre [fonctions d'assistance](../mfc/reference/collection-class-helpers.md) et [SerializeElements](../Topic/SerializeElements.md).  Pour plus d'informations sur l'implémentation de ces fonctions, consultez [Implémenter des fonctions d'assistance](#_core_implementing_helper_functions).  
  
 Cet exemple illustre la déclaration d'une liste d'entiers.  Le premier paramètre à l'étape 1 est le type de données stockées en tant qu'éléments dans la liste.  Le deuxième paramètre spécifie comment les données doivent être passée et retournée les fonctions membres de la classe de collection, telles que **Ajouter** et `GetAt`.  
  
##  <a name="_core_implementing_helper_functions"></a> Implémentation des fonctions d'assistance  
 Les classes de collection de `CArray`TEMPLATE, `CList`, et cinq fonctions d'assistance globales d'utilisation  `CMap` que vous pouvez personnaliser autant que nécessaire pour votre classe de collection dérivée.  Pour plus d'informations sur ces fonctions d'assistance, consultez [Programmes d'assistance de classe de collection](../mfc/reference/collection-class-helpers.md) dans *le guide de MFC*.  L'implémentation de la fonction de sérialisation est nécessaire pour la plupart des utilisations de classes de la collection sur template.  
  
###  <a name="_core_serializing_elements"></a> Sérialiser des éléments  
 Les classes `CArray`, `CList`, et `CMap` appellent `SerializeElements` pour stocker des éléments de collecte ou pour la lecture d'une archive.  
  
 L'implémentation par défaut de la fonction d'assistance de `SerializeElements` effectue une écriture de bits des objets à l'archive, ou une lecture au niveau de l'archivage des objets, selon que les objets sont stockées dans ou extraites de l'archivage.  Remplacez `SerializeElements` si cette opération n'est pas appropriée.  
  
 Si la collection contient des objets dérivés `CObject` et vous utilisez la macro `IMPLEMENT_SERIAL` dans l'implémentation de la classe d'éléments de collection, vous pouvez tirer parti des fonctionnalités de sérialisation intégrée à `CArchive` et `CObject`:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_3.cpp)]  
  
 Les opérateurs surchargés d'insertion pour `CArchive` appellent `CObject::Serialize` \(ou une substitution de cette fonction\) pour chaque objet de **CPerson**.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> Utilisation des classes des collections non typées  
 MFC gère également des classes de collection introduites avec la version 1,0 de MFC.  Ces classes ne sont pas fondées sur les classes ODBC MFC.  Elles peuvent être utilisées pour contenir les données des types pris en charge `CObject*`, **UINT**, `DWORD`, et `CString`.  Vous pouvez utiliser ces collections prédéfinies \(comme `CObList`\) pour gérer des collections de tous les objets dérivés de `CObject`.  MFC permet également d'autres collections prédéfinies pour gérer des types primitifs tels que **UINT** et des pointeurs voids`void`\(\*\).  En général toutefois, il est souvent pratique de définir vos propres collections de type sécurisé pour stocker des objets de plusieurs classe spécifique et ses dérivée.  Notez que fait à l'aide de classes de collection pas basées sur des modèles comprend plus de travail d'utiliser les classes TEMPLATE sur.  
  
 Il existe deux manières de créer des collections de type sécurisé avec les collections basées sur les modèles :  
  
1.  Utilisez des collections basées sur les modèles, le type de la conversion si nécessaire.  Il s'agit de l'approche plus facile.  
  
2.  Dériver de et étendez collection de type sécurisé basée sur des modèles.  
  
#### Pour utiliser des collections basées sur les modèles avec la conversion de type  
  
1.  Utilisez l'une des classes basées sur des modèles, telles que `CWordArray`.  
  
     Par exemple, vous pouvez créer `CWordArray` et ajouter toutes les valeurs 32 bits à lui, les récupérer.  Il n'existe aucune autre à effectuer.  Vous utilisez uniquement la fonctionnalité prédéfinie.  
  
     Vous pouvez également utiliser une collection prédéfinies, par exemple `CObList`, pour conserver tous les objets dérivés `CObject`.  Une collection `CObList` est définie pour contenir les pointeurs vers `CObject`.  Lorsque vous récupérez un objet dans la liste, vous devrez peut\-être convertir le résultat en type approprié les fonctions `CObList` retournent des pointeurs vers `CObject`.  Par exemple, si vous stockez des objets `CPerson` dans une collection `CObList`, vous devez convertir un élément récupéré pour être un pointeur vers un objet `CPerson`.  L'exemple suivant utilise une collection `CObList` pour gérer les objets `CPerson` :  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_4.cpp)]  
  
     Cette technique d'un type de collecte prédéfini et de conversion nécessaire peut être adéquate pour plusieurs de vos besoins à la collection.  Si vous avez plus besoin de fonctionnalités ou plus de la cohérence des types, utilisez une classe basée TEMPLATE, ou suivez la procédure suivante.  
  
#### Faire dériver de et étendez collection de type sécurisé basée sur des modèles.  
  
1.  Dériver votre propre classe de collection de l'une des classes basées sur des modèles prédéfinis.  
  
     Lorsque vous dérivez votre classe, vous pouvez ajouter des fonctions wrapper de type sécurisé pour fournir une interface de type sécurisé à des fonctions.  
  
     Par exemple, si vous dériviez une liste `CObList` pour gérer les objets `CPerson`, vous pouvez ajouter des fonctions wrapper `AddHeadPerson` et `GetHeadPerson`, comme indiqué ci\-dessous.  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/CPP/how-to-make-a-type-safe-collection_5.h)]  
  
     Ces fonctions wrapper permettent une manière sécurisée d'ajouter et de récupérer des objets de `CPerson` de la liste dérivée.  Vous pouvez voir que de la fonction `GetHeadPerson`, vous encapsulez simplement la conversion de type.  
  
     Vous pouvez également ajouter une nouvelle fonctionnalité en définissant les nouvelles fonctionnalités qui étendent les fonctionnalités de la collection plutôt que juste encapsulant les fonctionnalités existantes de wrapper de type sécurisé.  Par exemple, l'article [Supprimer tous les objets dans une collection de CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md) décrit la fonction pour supprimer tous les objets contenus dans une liste.  Cette fonction peut être ajoutée à cette classe dérivée comme une fonction membre.  
  
## Voir aussi  
 [Collections](../mfc/collections.md)
---
title: 'Comment : définir une Collection de Type sécurisé | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcd1fbce9e6dda649da8fe2e53fc7dc70db1da33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-a-type-safe-collection"></a>Comment : définir une collection de type sécurisé
Cet article explique comment créer des collections de types cohérents pour vos propres types de données. Les rubriques traitées ici sont les suivantes :  
  
-   [À l’aide des classes basées sur le modèle de sécurité de type](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [Implémentation des fonctions d’assistance](#_core_implementing_helper_functions)  
  
-   [À l’aide des classes de collection](#_core_using_nontemplate_collection_classes)  
  
 La bibliothèque MFC fournit les collections de type sécurisé prédéfinies basées sur des modèles C++. Étant donné qu'il s'agit de modèles, ces classes offrent une cohérence des types et simplifient l'utilisation sans conversion de type, ainsi que bien d'autres tâches liées à l'utilisation d'une classe non basée sur un modèle. L’exemple MFC [collecter](../visual-cpp-samples.md) illustre l’utilisation des classes de collection basées sur un modèle dans une application MFC. En général, utilisez ces classes lorsque vous entrez un nouveau code de collections.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> À l’aide des Classes basées sur le modèle de sécurité de Type  
  
#### <a name="to-use-template-based-classes"></a>Pour utiliser des classes basées sur des modèles  
  
1.  Déclarez une variable du type de classe de collection. Par exemple :  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  Appelez la fonction membre de l’objet de la collection. Par exemple :  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  Si nécessaire, implémentez le [fonctions d’assistance](../mfc/reference/collection-class-helpers.md) et [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements). Pour plus d’informations sur l’implémentation de ces fonctions, consultez [mise en œuvre les fonctions d’assistance](#_core_implementing_helper_functions).  
  
 Cet exemple illustre la déclaration d'une liste d'entiers. Le premier paramètre de l'étape 1 est le type de données stockées en tant qu'éléments dans la liste. Le deuxième paramètre spécifie comment les données doit être passé à et retournées à partir de fonctions membres de la classe de collection, tel que **ajouter** et `GetAt`.  
  
##  <a name="_core_implementing_helper_functions"></a> Implémentation des fonctions d’assistance  
 Les classes de collection basées sur les modèles `CArray`, `CList` et `CMap` utilisent cinq fonctions d'assistance globales que vous pouvez personnaliser autant que nécessaire pour votre classe de collection dérivée. Pour plus d’informations sur ces fonctions d’assistance, consultez [Assistants de classe de Collection](../mfc/reference/collection-class-helpers.md) dans les *référence MFC*. L’implémentation de la fonction de sérialisation est nécessaire pour la plupart des utilisations de classes de collection basées sur un modèle.  
  
###  <a name="_core_serializing_elements"></a> Sérialiser des éléments  
 Les classes `CArray`, `CList` et `CMap` appellent `SerializeElements` pour stocker des éléments de collection ou pour la lecture d'une archive.  
  
 L'implémentation par défaut de la fonction d'assistance de `SerializeElements` effectue une écriture de bits sur les objets de l'archive, ou une lecture au niveau de l'archivage des objets, selon que les objets sont stockés ou extraits de l'archive. Remplacez `SerializeElements` si cette opération n'est pas appropriée.  
  
 Si la collection contient des objets dérivés `CObject` et que vous utilisez la macro `IMPLEMENT_SERIAL` dans l'implémentation de la classe d'éléments de collection, vous pouvez tirer parti des fonctionnalités de sérialisation intégrée dans `CArchive` et `CObject` :  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]  
  
 Les opérateurs d’insertion surchargés pour `CArchive` appeler `CObject::Serialize` (ou une fonction de substitution) pour chaque **CPerson** objet.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> À l’aide des Classes de Collection  
 MFC gère également des classes de collection introduites avec la version 1.0 de MFC. Ces classes ne sont pas basées sur les modèles. Elles peuvent servir à contenir des données des types pris en charge `CObject*`, **UINT**, `DWORD`, et `CString`. Vous pouvez utiliser ces collections prédéfinies (comme `CObList`) pour gérer les collections de tous les objets dérivés de `CObject`. MFC fournit également d’autres collections prédéfinies pour gérer les types primitifs tels que **UINT** et des pointeurs void (`void`*). Toutefois, il est souvent pratique de définir vos propres collections de types cohérents pour stocker des objets de plusieurs classes spécifiques et ses dérivés. Notez que l’utilisation des classes de collection non basées sur des modèles nécessite plus de travail que l’utilisation des classes générées à partir de modèle.  
  
 Il existe deux manières de créer des collections de types cohérents avec les collections basées sur les modèles :  
  
1.  Utilisez des collections non basées sur les modèles, avec la conversion de type, si nécessaire. Il s'agit de l'approche la plus simple.  
  
2.  Dérivez ou étendez une collection de types cohérents non basés sur des modèles.  
  
#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Pour utiliser des collections non basées sur des modèles avec la conversion de type  
  
1.  Utilisez directement l'une des classes basées sur des modèles, telles que `CWordArray`.  
  
     Par exemple, vous pouvez créer `CWordArray` et lui ajouter toutes les valeurs 32 bits avant de les récupérer. Il n'y a rien d'autre à faire. Utilisez uniquement la fonctionnalité prédéfinie.  
  
     Vous pouvez également utiliser une collection prédéfinie, par exemple `CObList`, pour conserver tous les objets dérivés `CObject`. Une collection `CObList` est définie pour contenir les pointeurs vers `CObject`. Lorsque vous récupérez un objet dans la liste, vous devrez peut-être convertir le résultat en type approprié puisque les fonctions `CObList` retournent des pointeurs vers `CObject`. Par exemple, si vous stockez les objets `CPerson` d'une collection `CObList`, vous devrez convertir un élément récupéré en pointeur vers un objet `CPerson`. L'exemple suivant utilise une collection `CObList` pour gérer les objets `CPerson` :  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]  
  
     Cette technique d’utilisation d’un type de collection prédéfini et de la conversion si nécessaire peut être adéquate pour vos besoins en matière de collection. Si vous avez d'une fonctionnalité avancée ou de la cohérence des types, utilisez une classe basée sur un modèle, ou suivez la procédure ci-après.  
  
#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Pour dériver et étendre une collection de types cohérents non basés sur des modèles  
  
1.  Faites dériver votre propre classe de collection de l’une des classes basées sur des modèles prédéfinis.  
  
     Lorsque vous dérivez votre classe, vous pouvez ajouter des fonctions wrapper de type cohérent pour fournir une interface de type cohérent aux fonctions existantes.  
  
     Par exemple, si vous avez dérivé une liste `CObList` pour gérer les objets `CPerson`, vous pourrez ajouter des fonctions wrapper `AddHeadPerson` et `GetHeadPerson`, comme indiqué ci-dessous.  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]  
  
     Ces fonctions wrapper fournissent un mode de type cohérent pour ajouter et récupérer des objets `CPerson` de la liste dérivée. Vous pouvez voir que pour la fonction `GetHeadPerson`, vous encapsulez simplement la conversion de type.  
  
     Vous pouvez également ajouter une nouvelle fonctionnalité en définissant de nouvelles fonctions qui étendent les capacités de la collection plutôt que de juste encapsuler les fonctionnalités existantes en types cohérents. Par exemple, l’article [suppression de tous les objets d’une Collection CObject](../mfc/deleting-all-objects-in-a-cobject-collection.md) décrit une fonction permettant de supprimer tous les objets contenus dans une liste. Cette fonction peut être ajoutée à cette classe dérivée comme une fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Collections](../mfc/collections.md)


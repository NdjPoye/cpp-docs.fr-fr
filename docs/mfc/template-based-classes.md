---
title: "Classes bas&#233;es sur un mod&#232;le | Microsoft Docs"
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
  - "tableaux (C++), classes"
  - "tableaux (C++), pointeurs"
  - "tableaux (C++), basées sur un modèle"
  - "CArray (classe), classes basées sur un modèle"
  - "CList (classe), classes basées sur un modèle"
  - "classes de collection, basées sur des modèles"
  - "collections, pointeur typé"
  - "CTypedPtrArray (classe), classes basées sur un modèle"
  - "CTypedPtrList (classe), classes basées sur un modèle"
  - "CTypedPtrMap (classe), classes basées sur un modèle"
  - "classes de collection MFC, basées sur un modèle"
  - "pointeurs, typés (collections)"
  - "classes de collection de tableaux simples"
  - "classes de collection de listes simples"
  - "collections basées sur un modèle simple"
  - "collections de classes basées sur un modèle"
  - "pointeurs typés"
  - "pointeurs typés, collections de"
  - "collections de type sécurisé"
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes bas&#233;es sur un mod&#232;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les classes de collection modèle de type sécurisé dans la version 3,0 de MFC et versions ultérieures.  Utiliser ces modèles pour créer des collections de type sécurisé est plus pratique et permet de fournir la cohérence des types de manière plus efficace que d'utiliser les classes de collection non basées sur des modèles.  
  
 MFC prédéfinit deux catégories de collections modèles :  
  
-   [Classes tableau, liste et map](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`, `CList`, `CMap`  
  
-   [Tables, listes, et map des pointeurs typés](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`  
  
 Toutes les classes de collection simples sont dérivées de la classe `CObject`, afin qu'elles héritent de la sérialisation, la création dynamique, et d'autres propriétés de `CObject`.  Les classes de collection de type de pointeur exigent que vous spécifiiez la classe que vous dérivez de — qui doit être l'une des collections basées sur les modèles de pointeur prédéfinies par MFC, tel que `CPtrList` ou `CPtrArray`.  La nouvelle classe de collection hérite de la classe de base spécifiée, et les fonctions membres de la nouvelle classe utilisent des appels encapsulés aux membres de la classe de base pour garantir la cohérence des types.  
  
 Pour plus d'informations sur les modèles C\+\+, consultez [Modèles](../cpp/templates-cpp.md) dans le *Guide de référence du langage C\+\+*.  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Utilisation du tableau, de liste, et des modèles du tableau  
 Pour utiliser les modèles simples de collection, vous devez connaître le type des données pouvant être stockées dans les collections et les paramètres à utiliser dans les déclarations de la collection.  
  
###  <a name="_core_simple_array_and_list_usage"></a> Utilisation de tableau simple et de liste  
 Les classes de tableau simple et de liste, [CArray](../mfc/reference/carray-class.md) et [CList](../mfc/reference/clist-class.md), prend deux paramètres : *TYPE* et `ARG_TYPE`.  Ces classes peuvent enregistrer tout type de données, que vous spécifiez dans le paramètre *type*:  
  
-   Types de données critiques C\+\+, tels que `int`, `char`, et **float**  
  
-   Structures et classes C\+\+  
  
-   D'autres types que vous définissez  
  
 Par souci de commodité et d'efficacité, vous pouvez utiliser le paramètre `ARG_TYPE` pour spécifier le type des arguments de fonction.  En général, vous spécifiez `ARG_TYPE` comme référence au type que vous avez spécifié dans le paramètre *type*.  Par exemple :  
  
 [!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/CPP/template-based-classes_1.cpp)]  
  
 Le premier exemple déclare une collection de tables, `myArray`, qui contient `int`S.  Le deuxième exemple déclare une collection de listes, `myList`, qui stocke `CPerson` les objets.  Certaines fonctions membres des classes de collection prennent les arguments dont le type est spécifié par le paramètre de modèle `ARG_TYPE`.  Par exemple, la fonction membre **Ajouter** de la classe `CArray` accepte un argument `ARG_TYPE`:  
  
 [!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/CPP/template-based-classes_2.cpp)]  
  
###  <a name="_core_simple_map_usage"></a> Utilisation de tableau associatif simple  
 La classe de tableau associatif simple, [CMap](../mfc/reference/cmap-class.md), prend quatre paramètres : *KEY*, `ARG_KEY`, *VALUE*, et `ARG_VALUE`.  Comme les classes de tableau et de liste, les classes de tableau associatif peuvent enregistrer tout type de données.  Contrairement aux tables et listes, qui classent et ordonnent les données qu'ils enregistrent, les tableaux associatifs associent les clés et les valeurs : Vous accédez à une valeur stockée dans une table en spécifiant la clé associée à la valeur.  Le paramètre *KEY* spécifie le type de données des clés utilisées pour accéder aux données stockées dans le tableau associatif.  Si le type de *KEY* est une structure ou une classe, le paramètre `ARG_KEY` est généralement une référence au type spécifié dans *KEY*.  Le paramètre *valeur* spécifie le type des éléments stockés dans le tableau associatif.  Si le type `ARG_VALUE` est une structure ou une classe, le paramètre `ARG_VALUE` est généralement une référence au type spécifié dans *VALUE*.  Par exemple :  
  
 [!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/CPP/template-based-classes_3.cpp)]  
  
 Le premier exemple stocke des valeurs `MY_STRUCT`, y accède par des clés `int`, et retourne les éléments accédés à partir des objets `MY_STRUCT` par référence.  Le deuxième exemple stocke des valeurs `CPerson`, y accède par des clés `CString`, et retourne les références aux objets accédés.  Cet exemple peut représenter un simple livre d'adresses, dans lequel vous recherchez les utilisateurs par leur nom.  
  
 Parce que le paramètre *KEY* est de type `CString` et le paramètre *de KEY\_TYPE* est de type `LPCSTR`, les clés sont stockées dans le tableau associatif en tant qu'éléments de type `CString` mais sont référencées dans comme fonctions telles que `SetAt` à travers les pointeurs de type `LPCSTR`.  Par exemple :  
  
 [!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/CPP/template-based-classes_4.cpp)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> Utilisation de modèles de pointeur de type  
 Pour utiliser les modèles simples de pointeurs de types, vous devez connaître le type des données pouvant être stockées dans les collections et les paramètres à utiliser dans les déclarations de la collection.  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> Tableau de pointeurs de type et utilisation de liste  
 Les classes de tableau de pointeurs de types et de liste, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) et [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), prennent deux paramètres : `BASE_CLASS` et *TYPE*.  Ces classes peuvent enregistrer tout type de données, que vous spécifiez dans le paramètre *type*:  Elles sont dérivées de l'une des classes de collection basées sur les modèles qui stocke des pointeurs ; vous spécifiez cette classe de base dans `BASE_CLASS`.  Pour les tables, utilisez `CObArray` ou `CPtrArray`.  Pour les listes, utilisez `CObList` ou `CPtrList`.  
  
 En effet, lorsque vous déclarez une collection selon, supposons `CObList`, la nouvelle classe hérite non seulement des membres de sa classe de base, mais indique également plusieurs fonctions de membre de type sécurisé et d'opérateurs qui aident à fournir des types sécurisés en encapsulant des appels aux membres de la classe de base.  Ces encapsulations gèrent toutes les conversions de types nécessaires.  Par exemple :  
  
 [!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/CPP/template-based-classes_5.cpp)]  
  
 Le premier exemple déclare un tableau de pointeurs de type, `myArray`, dérivé de `CObArray`.  La table stocke et retourne des pointeurs sur les objets `CPerson` \(où `CPerson` est une classe dérivée de `CObject`\).  Vous pouvez appeler une fonction membre `CObArray`, ou vous pouvez appeler de nouvelles fonctions de type sécurisé `GetAt` et `ElementAt` ou utiliser l'opérateur de type sécurisé **\[ \]**.  
  
 Le deuxième exemple déclare une liste de pointeur de type, `myList`, dérivé de `CPtrList`.  La liste enregistre et retourne des pointeurs aux objets `MY_STRUCT`.  Une classe basée sur `CPtrList` est utilisée pour stocker les pointeurs sur les objets non dérivés de `CObject`.  `CTypedPtrList` a plusieurs fonctions membres de type sécurisé : `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, et `GetAt`.  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a> Utilisation de tableau associatif de pointeur de type  
 La classe de tableau associatif de pointeur de type, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), accepte trois paramètres : `BASE_CLASS`, *KEY*, et *valeurs*.  Le paramètre `BASE_CLASS` spécifie la classe à partir de laquelle dérive la nouvelle classe : `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`, et ainsi de suite.  *KEY* est analogue *KEY* dans `CMap`: Il spécifie le type de la clé utilisée pour les recherches.  *Valeur* est analogue *Valeur* dans `CMap`: Il spécifie le type d'objet stocké dans la carte.  Par exemple :  
  
 [!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/CPP/template-based-classes_6.cpp)]  
  
 Le premier exemple est un tableau associatif basé sur **CMapPtrToPt**r — il utilise des clés `CString` mappées aux pointeurs vers `MY_STRUCT`.  Vous pouvez rechercher un pointeur stocké en appelant une fonction membre de type sécurisé `Lookup`.  Vous pouvez utiliser l'opérateur **\[ \]** pour rechercher un pointeur stockée et l'ajouter si introuvable.  Et vous pouvez parcourir le tableau associatif à l'aide de la fonction de type sécurisé `GetNextAssoc`.  Vous pouvez également appeler d'autres fonctions membres de la classe `CMapPtrToPtr`.  
  
 Le deuxième exemple est un tableau associatif basé sur **CMapStringToO**b — il utilise des clés de chaîne mappées aux pointeurs stockés aux objets `CMyObject`.  Vous pouvez utiliser les mêmes membres de type sécurisé décrits dans le paragraphe précédent, ou vous pouvez appeler des membres de la classe `CMapStringToOb`.  
  
> [!NOTE]
>  Si vous spécifiez une **classe** ou un type `struct` pour le paramètre *valeur*, plutôt qu'un pointeur ou une référence au type, la classe ou la structure doit avoir un constructeur de copie.  
  
 Pour plus d'informations, consultez [Comment faire une collection de type sécurisé](../mfc/how-to-make-a-type-safe-collection.md).  
  
## Voir aussi  
 [Collections](../mfc/collections.md)
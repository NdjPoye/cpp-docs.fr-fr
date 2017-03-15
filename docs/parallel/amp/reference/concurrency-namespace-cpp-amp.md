---
title: "Accès concurrentiel Namespace (C++ AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: a62955c94771320a64027f4f820434dd5e7984a1
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-c-amp"></a>Concurrency, espace de noms (C++ AMP)
Fournit des classes et des fonctions qui accélèrent l’exécution de code C++ sur un matériel parallèle de données. Pour plus d’informations, consultez [présentation de C++ AMP](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="namespaces"></a>Espaces de noms  
  
|Nom|Description|  
|----------|-----------------|  
|[Concurrency::Direct3D Namespace](concurrency-direct3d-namespace.md)|Fournit des fonctions qui prennent en charge l’interopérabilité D3D. Permet l’utilisation transparente des D3D ressources de calcul dans le code de l’AMP et l’utilisation de ressources créées dans le code D3D, de gestion du matériel sans créer des copies redondantes intermédiaires. Vous pouvez utiliser C++ AMP incrémentielle accélérer les sections beaucoup de vos applications DirectX et l’utilisation de l’API D3D sur les données générées à partir de calculs AMP.|  
|[Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)|Les fonctions dans le `fast_math` espace de noms ne sont pas compatibles C99. Simple précision uniquement les versions de chaque fonction sont fournies. Ces fonctions utilisent les fonctions intrinsèques DirectX qui sont plus rapides que les fonctions correspondantes dans le `precise_math` espace de noms et ne nécessitent pas de prise en charge de double précision étendue sur l’accélérateur, mais elles sont moins précises. Il existe deux versions de chaque fonction pour la compatibilité au niveau de la source avec code C99 ; les deux versions acceptent et retournent des valeurs de précision simple.|  
|[Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)|Fournit des types et des fonctions qui sont conçues pour la programmation graphique.|  
|[Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)|Les fonctions dans le `precise_math` espace de noms sont C99 conforme. Les versions de chaque fonction simple précision et double précision sont incluses. Ces fonctions, y compris les fonctions simple précision — requièrent la prise en charge de double précision étendue sur l’accélérateur.|  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator, classe](accelerator-class.md)|Représente une abstraction d’un nœud physique calcul optimisé du point de distribution.|  
|[accelerator_view, classe](accelerator-view-class.md)|Représente une abstraction de périphérique virtuel sur un accélérateur de parallèle de données C++ AMP.|  
|[accelerator_view_removed, classe](accelerator-view-removed-class.md)|Exception levée lorsqu’un appel de DirectX sous-jacent échoue car le mécanisme de délai d’attente détection et récupération de Windows.|  
|[Array, classe](array-class.md)|Un agrégat de données un `accelerator_view` dans le domaine de la grille. Il est une collection de variables, un pour chaque élément dans un domaine de la grille. Chaque variable contient une valeur qui correspond à un type C++.|  
|[array_view, classe](array-view-class.md)|Représente une vue de données dans un tableau\<T, N >.|  
|[completion_future, classe](completion-future-class.md)|Représente un futur qui correspond à une opération asynchrone de C++ AMP.|  
|[extent, classe](extent-class.md)|Représente un vecteur de valeurs entières N qui spécifient les limites d’un espace à N dimensions qui a une origine de 0. Les valeurs du vecteur de coordonnées sont triés du plus significatif au moins significatif. Par exemple, dans un espace 3D cartésien, le vecteur de mesure (7,5,3) représente un espace dans lequel la coordonnée z comprise entre 0 et 7, les plages de coordonnée y de 0 à 5, et la coordonnée x est compris entre 0 et 3.|  
|[index, classe](index-class.md)|Définit un point d’index à N dimensions.|  
|[invalid_compute_domain, classe](invalid-compute-domain-class.md)|L’exception qui est levée lorsque le runtime ne peut pas démarrer un noyau à l’aide du domaine de calcul spécifié à la `parallel_for_each` site d’appel.|  
|[out_of_memory, classe](out-of-memory-class.md)|Exception levée lorsqu’une méthode échoue en raison d’un manque de mémoire système ou périphérique.|  
|[runtime_exception, classe](runtime-exception-class.md)|Le type de base pour les exceptions dans la bibliothèque C++ AMP.|  
|[tile_barrier, classe](tile-barrier-class.md)|Une classe de fonctionnalité qui n’est peut être créé par le système et est transmise à une mosaïque `parallel_for_each` lambda dans le cadre de le `tiled_index` paramètre. Il fournit une méthode, `wait()`, dont l’objectif consiste à synchroniser l’exécution des threads qui s’exécutent dans le groupe de threads (mosaïque).|  
|[tiled_extent, classe](tiled-extent-class.md)|A `tiled_extent` objet est un `extent` objet d’un à trois dimensions qui divise l’espace d’étendue en mosaïques unidimensionnels, à deux dimensions ou en trois dimensions.|  
|[tiled_index, classe](tiled-index-class.md)|Fournit un index dans une `tiled_grid` objet. Cette classe possède des propriétés pour accéder à élément par rapport à l’origine de la vignette local et par rapport à l’origine global.|  
|[uninitialized_object, classe](uninitialized-object-class.md)|Exception levée lorsqu’un objet non initialisé est utilisé.|  
|[unsupported_feature, classe](unsupported-feature-class.md)|Exception levée lorsqu’une fonctionnalité non prise en charge est utilisée.|  
  
### <a name="enumerations"></a>Énumérations  
  
|Nom|Description|  
|----------|-----------------|  
|[access_type, énumération](concurrency-namespace-enums-amp.md#access_type)|Spécifie le type d’accès aux données.|  
|[Énumération queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)|Spécifie les modes de files d’attente qui sont pris en charge sur l’accélérateur.|  
  
### <a name="operators"></a>Opérateurs  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[opérateur ==, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Détermine si les structures de données spécifiés sont égaux.|  
|[opérateur ! =, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Détermine si les structures de données spécifiés sont inégaux.|  
|[operator +, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Calcule la somme de component-wise des arguments spécifiés.|  
|[operator-, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Calcule la différence component-wise entre les arguments spécifiés.|  
|[opérateur * (opérateur) (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Calcule le produit component-wise des arguments spécifiés.|  
|[opérateur /, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Calcule le quotient component-wise des arguments spécifiés.|  
|[operator%, opérateur (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Calcule le modulo du premier argument spécifié par le deuxième argument spécifié.|  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[all_memory_fence, fonction](concurrency-namespace-functions-amp.md#all_memory_fence)|Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire ont été effectuées.|  
|[amp_uninitialize, fonction](concurrency-namespace-functions-amp.md#amp_uninitialize)|N’initialise pas le runtime C++ AMP.|  
|[atomic_compare_exchange, fonction](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Surchargé. Si la valeur stockée à l’emplacement spécifié valeur est égale à la première valeur spécifiée, la seconde valeur spécifique est stockée dans le même emplacement comme une opération atomique.|  
|[atomic_exchange, fonction](concurrency-namespace-functions-amp.md#atomic_exchange)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_add, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la somme de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_and, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `and` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_dec, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Surchargé. Décrémente la valeur stockée à l’emplacement spécifié et stocke le résultat dans le même emplacement que d’une opération atomique.|  
|[atomic_fetch_inc, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Surchargé. Incrémente la valeur stockée à l’emplacement spécifié et stocke le résultat dans le même emplacement que d’une opération atomique.|  
|[atomic_fetch_max, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la plus grande de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_min, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la plus petite de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_or, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `or` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_sub, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la différence entre cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_xor, fonction](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `xor` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[Copy (fonction)](concurrency-namespace-functions-amp.md#copy)|Copie un objet C++ AMP. Toutes les conditions de transfert de données synchrone sont remplies. Impossible de copier les données lorsque le code s’exécute le code sur un accélérateur. La forme générale de cette fonction est `copy(src, dest)`.|  
|[copy_async, fonction](concurrency-namespace-functions-amp.md#copy_async)|Copie un objet C++ AMP et retourne [completion_future](completion-future-class.md) qui peut être attendu. Impossible de copier les données lorsque le code s’exécute sur un accélérateur. La forme générale de cette fonction est `copy(src, dest)`.|  
|[direct3d_abort (fonction)](concurrency-namespace-functions-amp.md#direct3d_abort)|Interrompt l’exécution d’une fonction qui possède le `restrict(amp)` clause de restriction.|  
|[direct3d_errorf (fonction)](concurrency-namespace-functions-amp.md#direct3d_errorf)|Affiche une chaîne de mise en forme pour Visual Studio **sortie** fenêtre et déclenche une [runtime_exception](runtime-exception-class.md) exception qui a la même mise en forme de chaîne.|  
|[direct3d_printf (fonction)](concurrency-namespace-functions-amp.md#direct3d_printf)|Affiche une chaîne de mise en forme pour Visual Studio **sortie** fenêtre. Elle est appelée à partir d’une fonction qui possède le `restrict(amp)` clause de restriction.|  
|[global_memory_fence, fonction](concurrency-namespace-functions-amp.md#global_memory_fence)|Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que l’accès à la mémoire globale toutes ont été effectuées.|  
|[parallel_for_each, fonction (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Exécute une fonction dans le domaine de calcul.|  
|[tile_static_memory_fence, fonction](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Bloque l’exécution de tous les threads dans une mosaïque jusqu'à `tile_static` accès mémoire ont été effectuées.|  
  
## <a name="constants"></a>Constantes  
  
|Nom|Description|  
|----------|-----------------|  
|[Hlsl_max_num_buffers, constante](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Le nombre maximal de mémoires tampons allouées par DirectX.|  
|[MODULENAME_MAX_LENGTH (constante)](concurrency-namespace-constants-amp.md#modulename_max_length)|Stocke la longueur maximale du nom du module. Cette valeur doit être identique sur le compilateur et le runtime.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
## <a name="see-also"></a>Voir aussi  
 [Référence (C++ AMP)](reference-cpp-amp.md)





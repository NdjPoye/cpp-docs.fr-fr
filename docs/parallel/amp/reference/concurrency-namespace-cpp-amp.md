---
title: "Concurrency, espace de noms (C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency (espace de noms)"
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency, espace de noms (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Fournit des classes et des fonctions qui accélèrent l’exécution de code C++ sur un matériel parallèle de données. Pour plus d’informations, consultez [Présentation de C++ AMP](../../../parallel/amp/cpp-amp-overview.md)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="namespaces"></a>Espaces de noms  
  
|Nom|Description|  
|----------|-----------------|  
|[Concurrency::Direct3D Namespace](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)|Fournit des fonctions qui prennent en charge l’interopérabilité D3D. Permet l’utilisation transparente des D3D ressources de calcul dans le code de l’AMP et l’utilisation de ressources créées dans le code D3D, de gestion du matériel sans créer des copies redondantes intermédiaires. Vous pouvez utiliser C++ AMP incrémentielle accélérer les sections beaucoup de vos applications DirectX et l’utilisation de l’API D3D sur les données générées à partir de calculs AMP.|  
|[Concurrency::fast_math Namespace](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)|Les fonctions dans le `fast_math` espace de noms ne sont pas compatibles C99. Simple précision uniquement les versions de chaque fonction sont fournies. Ces fonctions utilisent les fonctions intrinsèques DirectX qui sont plus rapides que les fonctions correspondantes dans le `precise_math` espace de noms et ne nécessitent pas de prise en charge de double précision étendue sur l’accélérateur, mais elles sont moins précises. Il existe deux versions de chaque fonction pour la compatibilité au niveau de la source avec code C99 ; les deux versions acceptent et retournent des valeurs de précision simple.|  
|[Concurrency::Graphics Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)|Fournit des types et des fonctions qui sont conçues pour la programmation graphique.|  
|[Concurrency::precise_math Namespace](../../../parallel/amp/reference/concurrency-precise-math-namespace.md)|Les fonctions dans le `precise_math` espace de noms sont C99 conforme. Les versions de chaque fonction simple précision et double précision sont incluses. Ces fonctions, y compris les fonctions simple précision — requièrent la prise en charge de double précision étendue sur l’accélérateur.|  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator, classe](../../../parallel/amp/reference/accelerator-class.md)|Représente une abstraction d’un nœud physique calcul optimisé du point de distribution.|  
|[accelerator_view, classe](../../../parallel/amp/reference/accelerator-view-class.md)|Représente une abstraction de périphérique virtuel sur un accélérateur de parallèle de données C++ AMP.|  
|[accelerator_view_removed, classe](../../../parallel/amp/reference/accelerator-view-removed-class.md)|Exception levée lorsqu’un appel de DirectX sous-jacent échoue car le mécanisme de délai d’attente détection et récupération de Windows.|  
|[Array, classe](../../../parallel/amp/reference/array-class.md)|Un agrégat de données un `accelerator_view` dans le domaine de la grille. Il est une collection de variables, un pour chaque élément dans un domaine de la grille. Chaque variable contient une valeur qui correspond à un type C++.|  
|[array_view, classe](../../../parallel/amp/reference/array-view-class.md)|Représente une vue des données dans un tableau \< T, N >.|  
|[completion_future, classe](../../../parallel/amp/reference/completion-future-class.md)|Représente un futur qui correspond à une opération asynchrone de C++ AMP.|  
|[Extent, classe](../../../parallel/amp/reference/extent-class-cpp-amp.md)|Représente un vecteur de valeurs entières N qui spécifient les limites d’un espace à N dimensions qui a une origine de 0. Les valeurs du vecteur de coordonnées sont triés du plus significatif au moins significatif. Par exemple, dans un espace 3D cartésien, le vecteur de mesure (7,5,3) représente un espace dans lequel la coordonnée z comprise entre 0 et 7, les plages de coordonnée y de 0 à 5, et la coordonnée x est compris entre 0 et 3.|  
|[index, classe](../../../parallel/amp/reference/index-class.md)|Définit un point d’index à N dimensions.|  
|[invalid_compute_domain, classe](../../../parallel/amp/reference/invalid-compute-domain-class.md)|L’exception qui est levée lorsque le runtime ne peut pas démarrer un noyau à l’aide du domaine de calcul spécifié à la `parallel_for_each` site d’appel.|  
|[out_of_memory, classe](../../../parallel/amp/reference/out-of-memory-class.md)|Exception levée lorsqu’une méthode échoue en raison d’un manque de mémoire système ou périphérique.|  
|[runtime_exception, classe](../../../parallel/amp/reference/runtime-exception-class.md)|Le type de base pour les exceptions dans la bibliothèque C++ AMP.|  
|[tile_barrier, classe](../../../parallel/amp/reference/tile-barrier-class.md)|Une classe de fonctionnalité qui n’est peut être créé par le système et est transmise à une mosaïque `parallel_for_each` lambda dans le cadre de le `tiled_index` paramètre. Il fournit une méthode, `wait()`, dont l’objectif consiste à synchroniser l’exécution des threads qui s’exécutent dans le groupe de threads (mosaïque).|  
|[tiled_extent, classe](../../../parallel/amp/reference/tiled-extent-class.md)|Un `tiled_extent` objet est un `extent` objet d’un à trois dimensions qui divise l’espace d’étendue en mosaïques unidimensionnels, à deux dimensions ou en trois dimensions.|  
|[tiled_index, classe](../../../parallel/amp/reference/tiled-index-class.md)|Fournit un index dans une `tiled_grid` objet. Cette classe possède des propriétés pour accéder à élément par rapport à l’origine de la vignette local et par rapport à l’origine global.|  
|[uninitialized_object, classe](../../../parallel/amp/reference/uninitialized-object-class.md)|Exception levée lorsqu’un objet non initialisé est utilisé.|  
|[unsupported_feature, classe](../../../parallel/amp/reference/unsupported-feature-class.md)|Exception levée lorsqu’une fonctionnalité non prise en charge est utilisée.|  
  
### <a name="enumerations"></a>Énumérations  
  
|Nom|Description|  
|----------|-----------------|  
|[access_type, énumération](../Topic/access_type%20Enumeration.md)|Spécifie le type d’accès aux données.|  
|[Énumération queuing_mode](../../../parallel/amp/reference/queuing-mode-enumeration.md)|Spécifie les modes de files d’attente qui sont pris en charge sur l’accélérateur.|  
  
### <a name="operators"></a>Opérateurs  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[opérateur ==, opérateur (C++ AMP)](../Topic/operator==%20Operator%20\(C++%20AMP\).md)|Détermine si les structures de données spécifiés sont égaux.|  
|[opérateur ! =, opérateur (C++ AMP)](../Topic/operator!=%20Operator%20\(C++%20AMP\).md)|Détermine si les structures de données spécifiés sont inégaux.|  
|[operator +, opérateur (C++ AMP)](../Topic/operator+%20Operator%20\(C++%20AMP\).md)|Calcule la somme de component-wise des arguments spécifiés.|  
|[operator-, opérateur (C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)1.md)|Calcule la différence component-wise entre les arguments spécifiés.|  
|[opérateur * (opérateur) (C++ AMP)](../Topic/operator*%20Operator%20\(C++%20AMP\).md)|Calcule le produit component-wise des arguments spécifiés.|  
|[opérateur /, opérateur (C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)2.md)|Calcule le quotient component-wise des arguments spécifiés.|  
|[operator%, opérateur (C++ AMP)](../Topic/operator%25%20Operator%20\(C++%20AMP\).md)|Calcule le modulo du premier argument spécifié par le deuxième argument spécifié.|  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[all_memory_fence, fonction](../Topic/all_memory_fence%20Function.md)|Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire ont été effectuées.|  
|[amp_uninitialize, fonction](../Topic/amp_uninitialize%20Function.md)|N’initialise pas le runtime C++ AMP.|  
|[atomic_compare_exchange, fonction](../Topic/atomic_compare_exchange%20Function.md)|Surchargé. Si la valeur stockée à l’emplacement spécifié valeur est égale à la première valeur spécifiée, la seconde valeur spécifique est stockée dans le même emplacement comme une opération atomique.|  
|[atomic_exchange, fonction](../Topic/atomic_exchange%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_add, fonction](../Topic/atomic_fetch_add%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la somme de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_and, fonction](../Topic/atomic_fetch_and%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `and` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_dec, fonction](../Topic/atomic_fetch_dec%20Function.md)|Surchargé. Décrémente la valeur stockée à l’emplacement spécifié et stocke le résultat dans le même emplacement que d’une opération atomique.|  
|[atomic_fetch_inc, fonction](../Topic/atomic_fetch_inc%20Function.md)|Surchargé. Incrémente la valeur stockée à l’emplacement spécifié et stocke le résultat dans le même emplacement que d’une opération atomique.|  
|[atomic_fetch_max, fonction](../Topic/atomic_fetch_max%20Function.md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la plus grande de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_min, fonction](../Topic/atomic_fetch_min%20Function.md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la plus petite de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_or, fonction](../Topic/atomic_fetch_or%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `or` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_sub, fonction](../Topic/atomic_fetch_sub%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à la différence entre cette valeur et la valeur spécifiée comme une opération atomique.|  
|[atomic_fetch_xor, fonction](../Topic/atomic_fetch_xor%20Function%20\(C++%20AMP\).md)|Surchargé. Définit la valeur stockée à l’emplacement spécifié à l’opérateur de bits `xor` de cette valeur et la valeur spécifiée comme une opération atomique.|  
|[Copy (fonction)](../Topic/copy%20Function.md)|Copie un objet C++ AMP. Toutes les conditions de transfert de données synchrone sont remplies. Impossible de copier les données lorsque le code s’exécute le code sur un accélérateur. La forme générale de cette fonction est `copy(src, dest)`.|  
|[copy_async, fonction](../Topic/copy_async%20Function.md)|Copie un objet C++ AMP et retourne [completion_future](../../../parallel/amp/reference/completion-future-class.md) qui peut être attendu. Impossible de copier les données lorsque le code s’exécute sur un accélérateur. La forme générale de cette fonction est `copy(src, dest)`.|  
|[direct3d_abort (fonction)](../Topic/direct3d_abort%20Function.md)|Interrompt l’exécution d’une fonction qui possède le `restrict(amp)` clause de restriction.|  
|[direct3d_errorf (fonction)](../Topic/direct3d_errorf%20Function.md)|Affiche une chaîne de mise en forme pour Visual Studio **sortie** fenêtre et déclenche une [runtime_exception](../../../parallel/amp/reference/runtime-exception-class.md) exception qui a la même mise en forme de chaîne.|  
|[direct3d_printf (fonction)](../Topic/direct3d_printf%20Function.md)|Affiche une chaîne de mise en forme pour Visual Studio **sortie** fenêtre. Elle est appelée à partir d’une fonction qui possède le `restrict(amp)` clause de restriction.|  
|[global_memory_fence, fonction](../Topic/global_memory_fence%20Function.md)|Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que l’accès à la mémoire globale toutes ont été effectuées.|  
|[parallel_for_each, fonction (C++ AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)|Exécute une fonction dans le domaine de calcul.|  
|[tile_static_memory_fence, fonction](../Topic/tile_static_memory_fence%20Function.md)|Bloque l’exécution de tous les threads dans une mosaïque jusqu'à `tile_static` accès mémoire ont été effectuées.|  
  
## <a name="constants"></a>Constantes  
  
|Nom|Description|  
|----------|-----------------|  
|[Hlsl_max_num_buffers, constante](../Topic/HLSL_MAX_NUM_BUFFERS%20Constant.md)|Le nombre maximal de mémoires tampons allouées par DirectX.|  
|[MODULENAME_MAX_LENGTH (constante)](../Topic/MODULENAME_MAX_LENGTH%20Constant.md)|Stocke la longueur maximale du nom du module. Cette valeur doit être identique sur le compilateur et le runtime.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
## <a name="see-also"></a>Voir aussi  
 [Référence (C++ AMP)](../../../parallel/amp/reference/reference-cpp-amp.md)




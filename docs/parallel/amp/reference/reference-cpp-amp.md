---
title: "Référence (C++ AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: cc654cedd8639377ab7011c91454f1508c730247
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="reference-c-amp"></a>Référence (C++ AMP)
Cette section contient des informations de référence pour le runtime C++ Accelerated les Massive Parallelism (C++ AMP).  
  
> [!NOTE]
>  La norme du langage C++ réserve l’utilisation des identificateurs commençant par un caractère de soulignement (`_`) aux implémentations telles que les bibliothèques. N’utilisez donc pas de noms commençant par un trait de soulignement dans votre code. Le comportement des éléments de code, dont les noms suivent cette convention n'est pas garanti et est susceptible de changer dans les futures mises à jour. Pour ces raisons, ces éléments de code ont été omis de cette documentation.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)  
 Fournit des classes et des fonctions qui permettent à l’accélération du code C++ sur du matériel parallèle de données.  
  
 [Concurrency::Direct3D Namespace](concurrency-direct3d-namespace.md)  
 Fournit des fonctions qui prennent en charge l’interopérabilité D3D. Permet l’utilisation transparente des D3D ressources de calcul dans le code de l’AMP et l’utilisation de ressources créées dans le code D3D, de gestion du matériel sans créer des copies redondantes intermédiaires. Vous pouvez utiliser C++ AMP incrémentielle accélérer les sections beaucoup de vos applications DirectX et l’utilisation de l’API D3D sur les données générées à partir de calculs AMP.  
  
 [Concurrency::fast_math Namespace](concurrency-fast-math-namespace.md)  
 Les fonctions dans le `fast_math` espace de noms ne sont pas compatibles C99. Simple précision uniquement les versions de chaque fonction sont fournies. Ces fonctions utilisent les fonctions intrinsèques DirectX qui sont plus rapides que les fonctions correspondantes dans le `precise_math` espace de noms et ne nécessitent pas de prise en charge de double précision étendue sur l’accélérateur, mais elles sont moins précises. Il existe deux versions de chaque fonction pour la compatibilité au niveau de la source avec code C99 ; les deux versions acceptent et retournent des valeurs de précision simple.  
  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)  
 Fournit des types et des fonctions qui sont conçues pour la programmation graphique.  
  
 [Concurrency::precise_math Namespace](concurrency-precise-math-namespace.md)  
 Les fonctions dans le `precise_math` espace de noms sont C99 conforme. Les versions de chaque fonction simple précision et double précision sont incluses. Ces fonctions, y compris les fonctions simple précision — requièrent la prise en charge de double précision étendue sur l’accélérateur.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C++ AMP accélère l’exécution de votre code C++ en tirant parti du matériel parallèle de données qui est généralement présent sous la forme d’une unité de traitement graphique (GPU) sur une carte graphique additionnelle.







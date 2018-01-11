---
title: forward_iterator_tag, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::forward_iterator_tag
dev_langs: C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4874163e1060658c03757507cba2953c35c56557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag, struct
Classe qui fournit un type de retour pour une fonction **iterator_category** représentant un itérateur vers l’avant.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>Notes  
 Les classes de balise de catégorie sont utilisées comme balises de compilation pour la sélection de l’algorithme. La fonction de modèle doit déterminer la catégorie la plus spécifique de son argument d’itérateur pour pouvoir utiliser l’algorithme le plus efficace au moment de la compilation. Pour chaque itérateur de type `Iterator`, `iterator_traits`< `Iterator`> **::iterator_category** doit être défini comme étant la balise de catégorie la plus spécifique qui décrit le comportement de l’itérateur.  
  
 Le type est identique à **iterator**\< **Iter**> **::iterator_category** quand **Iter** décrit un objet pouvant servir d’itérateur vers l’avant.  
  
## <a name="example"></a>Exemple  
 Consultez [iterator_traits](../standard-library/iterator-traits-struct.md) ou [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) pour obtenir un exemple d’utilisation des **iterator_tag**s.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [input_iterator_tag, struct](../standard-library/input-iterator-tag-struct.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




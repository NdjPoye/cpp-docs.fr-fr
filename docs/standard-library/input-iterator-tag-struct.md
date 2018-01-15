---
title: input_iterator_tag, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::input_iterator_tag
dev_langs: C++
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 267e4109f5a1b0447dd1c7b2b61796a2346694f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag, struct
Classe qui fournit un type de retour pour une fonction **iterator_category** représentant un itérateur d’entrée.  
  
## <a name="syntax"></a>Syntaxe  
  
struct input_iterator_tag {};  
  
## <a name="remarks"></a>Notes  
 Les classes de balise de catégorie sont utilisées comme balises de compilation pour la sélection de l’algorithme. La fonction de modèle doit rechercher la catégorie la plus spécifique de son argument d’itérateur, pour pouvoir utiliser l’algorithme le plus efficace au moment de la compilation. Pour chaque itérateur de type `Iterator`, `iterator_traits`< `Iterator`> **::iterator_category** doit être défini comme étant la balise de catégorie la plus spécifique qui décrit le comportement de l’itérateur.  
  
 Le type est identique à **iterator**\< **Iter**> **::iterator_category** quand **Iter** décrit un objet pouvant servir d’itérateur d’entrée.  
  
## <a name="example"></a>Exemple  
 Consultez [iterator_traits](../standard-library/iterator-traits-struct.md) ou [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) pour obtenir un exemple montrant comment utiliser des balises **iterator_tag**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<iterator>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)


